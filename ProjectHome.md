My opengl image library.

This is the currently supported file type.

  * PEG baseline (no JPEG progressive)
  * NG 8-bit only

  * GA (not sure what subset, if a subset)
  * MP non-1bpp, non-RLE
  * SD (composited view only, no extra channels)

  * IF (**comp always reports as 4-channel)
  * DR (radiance rgbE format)
  * IC (Softimage PIC)**

Usage Example

Build Texture from a file.

stub:
```
GLuint BuildTexture(const char * filename, bool invertimg = false, bool grayscale = false, bool gentexcoords = false, bool buildMipMap = false, bool addalpha = false);
```

ex.
```
GLuint _SkyBox[6];
_SkyBox[location] = CZAIL::BuildTexture(filename, inverttex, grayscale);
```

Get image data

stub:
```
unsigned char *GetTextureData(const char * filename,int &width, int &height,int &channels, bool invertimg = false, bool grayscale = false );
```

ex.
```
unsigned char * image = CZAIL::GetTextureData(heightmap, w, h,channels, true);
```

Build a colored texture

stub
```
GLuint BuildColorTexture(unsigned char r, unsigned char g, unsigned char b);
```

ex.
```
Materials[j].tex = CZAIL::BuildColorTexture(r, g, b);
```