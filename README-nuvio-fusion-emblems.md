# Nuvio Fusion Emblems

`nuvio-fusion-emblems.json` is a **universal Nuvio Fusion badge pack** that uses the coloured logos already stored in this repository. It adds two groups of emblems to stream results: **Streaming Platforms** and **Studios**.

The pack contains 42 enabled rules: 17 streaming platforms and 25 studios. It checks the whole stream card, case-insensitively, so it works with standard Nuvio sources and does not require an AIOStreams formatter. A badge appears only when its service or studio name (or a recognised tag such as `NF`, `AMZN`, `DSNP`, or `ATVP`) is present in the stream metadata.

## Import in Nuvio

On Android TV, open **Settings → Layout → Streams → Fusion Badge URLs**. On Mobile, Desktop, or Web, open **Settings → Streams → Fusion Badge URLs**. Paste the raw URL below, choose **Import**, then ensure this pack is the active one.

```text
https://raw.githubusercontent.com/TrainAgain2/resource.images.studios.coloured/master/nuvio-fusion-emblems.json
```

Nuvio stores the rules after import. It can remember up to three sources, but only one badge pack is active at a time.

## Coverage

| Group | Included emblems |
| --- | --- |
| Streaming platforms | Netflix, Prime Video, Apple TV+, Disney+, Max, Hulu, Paramount+, Peacock, AMC+, Starz, Showtime, MUBI, Criterion, Shudder, BritBox, Viaplay, Stan |
| Studios | Warner Bros., Universal, Walt Disney, Sony Pictures, Paramount Pictures, Lionsgate, A24, 20th Century, New Line Cinema, DreamWorks, Columbia Pictures, Marvel Studios, Lucasfilm, MGM, Miramax, Focus Features, Searchlight, STUDIOCANAL, Legendary, Amblin, Bad Robot, Blumhouse, Plan B, Skydance, Working Title |

## Notes

The JSON references the repository's existing `resources/*.png` files through stable GitHub Raw URLs; no image assets are duplicated. The original icon collection is licensed under **CC BY-SA 3.0 US** as stated in [`LICENSE.txt`](LICENSE.txt). Changes to patterns, colours, and enabled states can be made directly in `nuvio-fusion-emblems.json` and then re-imported into Nuvio.
