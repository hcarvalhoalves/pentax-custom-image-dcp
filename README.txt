Pentax Custom Image DCP (DNG Camera Profiles)

This repository contains DCP files that match PENTAX's in-camera Custom Image profiles. This allows applying the look to PENTAX-produced DNG files in an external software.

These profiles are constructed by reverse-engineering the 3x3 look matrices that PENTAX implemented as Custom Image profiles in-camera, and tuned for the DNG Color Matrix embedded on the DNG files for each camera.

Gold and Cross Processing are mostly three per-channel RGB curves, taken from PENTAX Digital Camera Utility 5, which tint greys. A DCP cannot do that, so the curves are in LUT/ as 1D .cube files. Apply them to the finished, sRGB-encoded render, after the profile and tone curve:

  Gold              Natural profile  + LUT/PENTAX Custom Image Gold.cube
  Cross Processing  Natural profile  + LUT/PENTAX Custom Image Cross Processing.cube

For software that cannot read DCP files, LUT/ also has every other look as a 3D .cube LUT, made from its profile. They take an sRGB image already rendered neutrally and return it in the look, sRGB in and sRGB out. LUT/README.txt describes the colour spaces and how to use them.

---

pentax-custom-image-dcp © 2026 Henrique Carvalho Alves.

This work is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).

To view a copy of this license, visit https://creativecommons.org/licenses/by/4.0/

PENTAX is a trademark or registered trademark of Ricoh Imaging Company, Ltd. in Japan and/or other countries. All other trademarks are the property of their respective owners.

The author of this repository is not affiliated with, endorsed by, or sponsored in any way by Ricoh Imaging Company, Ltd.
