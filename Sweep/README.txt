Sweep renders

A check for discontinuities and clipping in the profiles: a synthetic raw rendered through each PENTAX KP profile in Revelar's renderer.

The raw is a LinearRaw DNG tagged as a PENTAX KP, so the KP profiles attach. It has three bands. Across, each band runs through every hue. Down, each band runs from the raw's clip (top) to 8 stops under (bottom). The bands are full saturation, 35% saturation and neutral. The raw's values are not real KP camera colours, so the hues and the tint on the neutral band mean nothing. Only how smoothly each band falls off does.

Gold and Cross Processing have no profile, only their 1D LUTs (LUT/). Their renders are the Natural profile, rendered with Revelar's gamut fitted to sRGB, with the LUT applied to the sRGB values, as LUT/README.txt describes.

The PNGs are Display P3, the space Revelar renders for the screen, and carry its ICC profile.

The table gives, per band, the largest change between adjacent rows (8-bit levels, any channel), then the number of places where luminance rises by more than one level as exposure falls. The first four rows and the last ten rows of each band are left out: they are edges of the test image and jump with no profile too (2.5, 1.6 and 1.5 levels in the three bands elsewhere).

                                   S=1            S=0.35         neutral
Natural                           13.6 /  0       2.1 /   0      2.0 /    0
Bright                            14.8 /  2       2.7 /   0      2.5 /    0
Portrait                          12.9 /  0       2.6 /   0      2.1 /    0
Landscape                         14.1 /  3       2.9 /   0      2.7 /    0
Vibrant                           14.6 /  2       4.1 /   0      2.7 /    0
Radiant                           13.2 /  2       5.1 /   0      3.4 /    0
Muted                              2.2 /  0       1.6 /   0      1.4 /    0
Bleach Bypass                      9.3 /  0       3.2 /   0      2.6 /    0
Reversal Film                     15.3 /  0       4.4 /   0      2.6 /    0
Monochrome                         2.0 /  0       2.0 /   0      1.7 /    0
SATOBI                            11.9 /  0       2.3 /   0      2.0 /    0
KATEN                             15.3 /  3       4.5 /   0      2.6 /    0
KYUSHU                             9.7 /  0       2.6 /   0      1.8 /    0
FUYUNO                             6.3 /  0       2.5 /   0      2.2 /    0
HARUBENI                          13.5 /  0       1.9 /   0      1.9 /    0
Gold                               5.8 /  0       3.8 /   0      3.7 /    0
Cross Processing                  11.0 /  0       4.0 /   0      3.6 /    0

At 35% saturation and on the neutral band every shipped profile is smooth. In the full-saturation band the larger steps are in yellow-greens (about 40 to 120 deg), one to three stops under the clip, where green reaches display white and red falls quickly; the few reversals are blues at 208 to 212 deg, where the KP matrix takes a channel below zero. Natural rendered without its tone curve shows the same steps, so they come from how the renderer maps colours that saturated, not from the profiles.

Rendered with Revelar f6ba0e4f, which fixed the thin vertical notches earlier renders showed in saturated blues and magentas.
