# Unity-kinect-V1-SDK
I took this Plugin in the Unity Asset store [MS Kinect SDK](https://api.unity.com/v1/oauth2/authorize?client_id=asset_store_v2&locale=en_US&redirect_uri=https%3A%2F%2Fassetstore.unity.com%2Fauth%2Fcallback%3Fredirect_to%3D%252Fpackages%252Ftools%252Fkinect-with-ms-sdk-7747%253Fsrsltid%253DAfmBOopA1aaeez98IPuPzgxZvRT6qKVBcIIulHjI4n2Xcqr0dIFwExm9&response_type=code&state=6cdc5f92-bb68-44d0-a2ef-3bd15385ee8f) and fixed it to work on newer unity versions

There is a working Kinect V2 unity SDK that's made by Microsoft [here](https://learn.microsoft.com/en-us/windows/apps/design/devices/kinect-for-windows)
but to my knowledge, there isn't (I couldn't find) an SDK for the Kinect V1 for Unity that works for the newer versions of Unity (newer than Unity 5.0 V 2018.3 )

Thanks to the original maker Rumen F, for keeping clear documentation in the code, I was able to create this version. 
Read more about the original SDK here: [MS Kinect SDK](https://rfilkov.com/2013/12/16/kinect-with-ms-sdk/)

the assest is not on GitHub

[link to my repo](https://github.com/ahmed-esh/Unity-kinect-V1-SDK/tree/main)

### Functions Added

#### `GetDirectionBetweenJoints`

The `GetDirectionBetweenJoints` function calculates the directional vector between two joints on the user’s body. This is crucial for applications that require understanding the orientation and relative movement of body parts. By knowing the direction from one joint to another, we can infer gestures and postures, enhancing interaction accuracy.

Here's the function:

```csharp
public Vector3 GetDirectionBetweenJoints(KinectInterop.JointType joint1, KinectInterop.JointType joint2, int userId)
{
    // Get the positions of the two joints
    Vector3 joint1Position = GetJointPosition(userId, (int)joint1);
    Vector3 joint2Position = GetJointPosition(userId, (int)joint2);
    
    // Calculate the direction vector and normalize it
    Vector3 direction = (joint2Position - joint1Position).normalized;

    return direction;
}
```

- **Parameters**:
  - `joint1` and `joint2`: These are the Kinect joints between which the direction is measured. They are passed in as `KinectInterop.JointType` enums.
  - `userId`: This identifies the specific user (or tracked skeleton) for whom the direction is calculated.

- **Returns**:
  - A `Vector3` normalized direction vector from `joint1` to `joint2`.

This function was instrumental for gesture-based functionalities, as it provided an intuitive way to determine where a body part was pointing relative to another. For instance, tracking the direction from the elbow to the wrist allows for fine-grained control in applications that require arm or hand gestures.

#### `void OnGUI()`

The `OnGUI` function was added for rendering real-time Kinect data to the screen. This is particularly useful during development for quick, visual feedback on tracked joint positions and user status. `OnGUI` functions are often used in Unity to create simple debugging interfaces, and in this case, it helps in checking the tracking accuracy and joint mappings.

Here’s an example implementation of the `OnGUI` function:

```csharp
void OnGUI()
{
    // Display Kinect status on the screen
    if (kinectManager && kinectManager.IsInitialized())
    {
        int usersCount = kinectManager.GetUsersCount();
        GUI.Label(new Rect(10, 10, 200, 20), "Tracked Users: " + usersCount);

        for (int i = 0; i < usersCount; i++)
        {
            int userId = kinectManager.GetUserIdByIndex(i);
            GUI.Label(new Rect(10, 30 + i * 20, 200, 20), "User ID: " + userId);
        }

        // Display joint positions for debugging purposes
        foreach (KinectInterop.JointType joint in Enum.GetValues(typeof(KinectInterop.JointType)))
        {
            Vector3 jointPosition = kinectManager.GetJointPosition(0, (int)joint);
            GUI.Label(new Rect(10, 60 + (int)joint * 20, 200, 20), joint + ": " + jointPosition);
        }
    }
    else
    {
        GUI.Label(new Rect(10, 10, 200, 20), "Kinect not initialized");
    }
}
```

- **Usage**:
  - The function first checks if the Kinect Manager is initialized.
  - It then retrieves and displays the count of tracked users and their IDs.
  - For each joint in the Kinect skeleton, the function displays the current position on the screen, updating in real-time.

This function is helpful during debugging to ensure the Kinect accurately tracks each joint, and it provides quick confirmation of joint positions without needing an external debugger. Implementing `OnGUI` allowed me to validate joint mapping and troubleshoot any misalignments directly in the Unity editor.

---

### Reflection on the Fix Process 

The hard part was figuring out what was wrong 
Unity has a very powerful compiler that can detct errors and help you fix your code which made my job easier 
and this is something I am really passioned about so the fix didn't take that
