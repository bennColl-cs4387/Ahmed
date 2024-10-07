[Link to Essay](https://docs.google.com/document/d/1ylT4trtCpMn4WUk3uHZyCcV_PPUi-Bfh8NGzd58L748/edit?usp=sharing)

# Outline to help me write:

### Project Overview:
I have chosen the open-source project **YouTubeExplode**, a popular library for interacting with YouTube, written primarily in **C#**. The main contributor is **Tyrrrz**, and the project is well-maintained with regular updates. Although YouTubeExplode is not part of a larger foundation, it has a solid community with clear guidelines and an active issue tracker.

This project is a good fit for me as it deals with a framework I'm familiar with—**.NET**—and offers an opportunity to contribute to a well-structured codebase.

### Why This is a Good Codebase:
I am particularly interested in this codebase because it aligns with my skills in C# and .NET, 

### Identified Issue:
The specific issue I plan to address is **"500 error when calling GetManifestAsync"** (Issue #782)【28†source】. The problem arises when trying to retrieve a stream manifest for very long videos (e.g., a 37-hour video), causing an `HttpRequestException`. 

A lot of memes and content come from downloading long videos and then cutting them into chunks 

This issue is significant because it impacts users attempting to download or work with long-duration YouTube videos, which are becoming more common due to streams and events. Technically, the error seems tied to YouTube’s handling of requests for long videos, and the bug was reproduced consistently.

There has been some community discussion, and it was initially marked as a transient YouTube issue, but further investigation showed that the bug was reproducible, specifically with long videos.

### Proposed Solution:
My proposed solution involves handling the specific edge case for long videos. Since the issue arises when requesting very long videos, I suggest updating the library to segment requests for videos longer than a certain threshold (e.g., 30 hours). This would involve breaking the video into smaller segments or adjusting how the range headers are sent during the manifest retrieval process.
