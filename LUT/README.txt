LUTs

Two kinds of .cube file are in this folder. Both work on finished, display-referred sRGB images, not on raw or scene-linear data.


3D LUTs: one per Custom Image look

  PENTAX Custom Image <look>.cube, LUT_3D_SIZE 33, for every look except Natural.

  Input:   sRGB: Rec.709 primaries, D65 white, the sRGB (IEC 61966-2-1) transfer function, values 0 to 1. The image should already be rendered neutrally: the app's own camera profile with no look or style added, and a tone curve close to PENTAX Natural's (a standard, medium-contrast curve). The closer the starting point is to Natural, the closer the result is to the camera.
  Output:  sRGB, the same encoding, values 0 to 1, clipped to the sRGB gamut.

  Each LUT turns a Natural rendering into the look's: its colour (the profile's LookTable) and its tone (its tone curve in place of Natural's). It is made from the look's DCP with the camera matrix left out, so one LUT serves every camera. There is no Natural LUT: it would change nothing.

  Use it as the last colour step, after exposure, white balance and tone adjustments, on an 8- or 16-bit sRGB image. In an app working in another space (Display P3, Adobe RGB, ProPhoto, linear, log), convert to sRGB first and back after, or the colours and tone will be wrong. Don't stack it on a DCP from this repository: the DCP already contains the look.

  Accuracy: applied with trilinear interpolation, the LUTs are within 0.07 to 0.63 OKLab dE x100 of the exact transform at the 99th percentile (a just-noticeable difference is about 1 to 2). The larger misses, up to about 7 for Radiant, are in the most saturated colours at the edge of the sRGB gamut.


1D LUTs: Gold and Cross Processing

  PENTAX Custom Image Gold.cube and PENTAX Custom Image Cross Processing.cube, LUT_1D_SIZE.

  Input:   sRGB-encoded RGB, values 0 to 1, the finished render after the profile and tone curve.
  Output:  sRGB-encoded RGB, values 0 to 1.

  Each is one curve per channel, from PENTAX Digital Camera Utility 5. They tint greys, which a DCP cannot do. Start from a Natural rendering (the Natural DCP, or a neutral render as above), then apply the curve.
