
# Matplotlib Issue #28809: Adding AVIF Format Support to `savefig`

## Problem Description

With the rise of the AVIF (AV1 Image File Format), many applications and libraries are beginning to support this image format due to its efficient compression and high quality. Currently, Matplotlib’s `savefig` function supports several output formats such as PNG, PDF, EPS, and WebP, but AVIF is not yet included. This feature request aims to add AVIF support, allowing users to save figures in this format directly from Matplotlib.

Adding AVIF support would be particularly beneficial for users who require high-quality, compressed images for web use, as AVIF can often yield smaller file sizes compared to formats like PNG or JPEG.

## Proposed Solution

The solution involves modifying Matplotlib’s backend to recognize `.avif` as a supported format and enabling the `savefig` function to use Pillow’s AVIF encoding capabilities. Pillow, the underlying image processing library for Matplotlib, supports AVIF as of version 8.2.0, which makes this update feasible.

### Implementation Steps

1. **Locate the `savefig` Function**:
   - In the Matplotlib codebase, `savefig` functionality is primarily managed within `backend_agg.py` (found in `lib/matplotlib/backends`).
   - Inside this file, `savefig` handles different formats like PNG and WebP.

2. **Update the List of Supported Formats**:
   - Locateing the list where supported formats are declared and add `'avif'` to this list.

   ```python
   supported_formats = ["png", "pdf", "ps", "eps", "svg", "webp", "avif"]
   ```

3. **Modify the `savefig` Function to Handle AVIF**:
   - In the `savefig` function, add a condition to recognize `.avif` as a valid format.
   - Ensureing the code passes the AVIF format to Pillow correctly.

4. **Test the Implementation**:
   - After making these changes, we test the updated `savefig` function.
  

### what I did so far
```python
  print_jpg.__doc__, print_tif.__doc__, print_webp.__doc__ = map(
    def print_avif(self, filename_or_obj, *, metadata=None, pil_kwargs=None):
    self._print_pil(filename_or_obj, "avif", pil_kwargs, metadata)


    print_jpg.__doc__, print_tif.__doc__, print_webp.__doc__, print_avif.__doc__ = map(
        """
```

[my fork](https://github.com/matplotlib/matplotlib/compare/main...ahmed-esh:matplotlib:%2328809%2C-Adding-AVIF?expand=1)
