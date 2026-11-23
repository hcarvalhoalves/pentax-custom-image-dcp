Sweep renders

A check for discontinuities and clipping in the profiles: a synthetic raw rendered through each PENTAX KP profile in Revelar's renderer.

The raw is a LinearRaw DNG tagged as a PENTAX KP, so the KP profiles attach. It has three bands. Across, each band runs through every hue. Down, each band runs from the raw's clip (top) to 8 stops under (bottom). The bands are full saturation, 35% saturation and neutral. The raw's values are not real KP camera colours, so the hues and the tint on the neutral band mean nothing. Only how smoothly each band falls off does.

"Natural, flat-top build (broken)" is an earlier build whose tone curves reached white at about 0.68 and stayed flat to 1. Revelar inverts the profile curve, and a flat top makes that inversion blow up, so highlights turned clipped cyan. The shipped profiles round off the last half stop instead. "Natural, before tone curves" is the Natural profile without a tone curve, as it was before the curves were added.

The table gives, per band, the largest change between adjacent rows (8-bit levels, any channel), then the number of places where luminance rises by more than one level as exposure falls. The first four rows and the last ten rows of each band are left out: they are edges of the test image and jump with no profile too.

                                   S=1            S=0.35         neutral
No profile                         2.5 /  0       1.6 /   0      1.5 /    0
Natural                           13.6 / 10       2.0 /   0      2.1 /    0
Bright                            14.8 / 13       2.7 /   0      2.6 /    0
Portrait                          13.6 / 10       2.6 /   0      2.2 /    0
Landscape                         14.8 / 14       2.9 /   0      2.8 /    0
Vibrant                           14.6 / 17       4.0 /   0      2.8 /    0
Radiant                           16.8 / 14       4.8 /   0      3.5 /    0
Muted                             10.9 / 13       1.6 /   0      1.4 /    0
Bleach Bypass                      9.6 /  2       3.2 /   0      2.6 /    0
Reversal Film                     19.1 / 11       4.4 /   0      2.6 /    0
Cross Processing                  13.7 / 11       2.0 /   0      2.1 /    0
Monochrome                         7.3 / 13       2.1 /   0      1.7 /    0
SATOBI                            15.1 / 11       2.3 /   0      2.0 /    0
KATEN                             20.0 / 15       4.6 /   0      2.6 /    0
KYUSHU                            14.8 / 13       2.6 /   0      1.8 /    0
FUYUNO                            17.6 / 13       2.5 /   0      2.2 /    0
HARUBENI                          13.6 / 10       1.9 /   0      2.0 /    0
Natural, flat-top build (broken)  91.3 / 18      88.1 / 694     29.5 / 3600
Natural, before tone curves       14.7 / 10       2.3 /   0      2.2 /    0

At 35% saturation and on the neutral band every shipped profile is smooth. In the full-saturation band the larger steps and the few reversals are at the gamut edge, mostly in one magenta column (the thin vertical line in the renders). The profile without a tone curve shows them too, so they come from how the renderer maps colours that saturated, not from the tone curves.
