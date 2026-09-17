# Nuvio Fusion Emblems

`nuvio-fusion-emblems.json` is a **universal Nuvio Fusion badge pack** that uses the coloured logos already stored in this repository. It adds three groups of emblems to stream results: **Servers / Addons**, **Streaming Platforms**, and **Studios**.

The pack contains 43 enabled rules: one server/addon, 17 streaming platforms, and 25 studios. It checks the whole stream card, case-insensitively, so it works with standard Nuvio sources and does not require an AIOStreams formatter. A badge appears only when its service, studio, source, or addon name (or a recognised tag such as `NF`, `AMZN`, `DSNP`, or `ATVP`) is present in the stream metadata.

## Import in Nuvio

On Android TV, open **Settings → Layout → Streams → Fusion Badge URLs**. On Mobile, Desktop, or Web, open **Settings → Streams → Fusion Badge URLs**. Paste the raw URL below, choose **Import**, then ensure this pack is the active one.

```text
https://raw.githubusercontent.com/TrainAgain2/resource.images.studios.coloured/master/nuvio-fusion-emblems.json
```

Nuvio stores the rules after import. It can remember up to three sources, but only one badge pack is active at a time.

## Coverage

| Group | Included emblems |
| --- | --- |
| Servers / Addons | AIOStreams, including the `AIOStreams Nightly` addon name |
| Streaming platforms | Netflix, Prime Video, Apple TV+, Disney+, Max, Hulu, Paramount+, Peacock, AMC+, Starz, Showtime, MUBI, Criterion, Shudder, BritBox, Viaplay, Stan |
| Studios | Warner Bros., Universal, Walt Disney, Sony Pictures, Paramount Pictures, Lionsgate, A24, 20th Century, New Line Cinema, DreamWorks, Columbia Pictures, Marvel Studios, Lucasfilm, MGM, Miramax, Focus Features, Searchlight, STUDIOCANAL, Legendary, Amblin, Bad Robot, Blumhouse, Plan B, Skydance, Working Title |

## Notes

Fusion emblems are rendered **only on stream result cards**. Nuvio matches stream fields that include filename, parsed tags, source name, and addon name. It does not run Fusion JSON rules on the movie or series detail page, so this pack cannot add studio or platform logos next to the IMDb/ratings row in that screen. That placement requires a feature in Nuvio itself or a metadata provider that exposes company logos.

The JSON references the repository's existing `resources/*.png` files through stable GitHub Raw URLs. `resources/AIOStreams.png` is the official white AIOStreams logo, sourced from the public [AIOStreams branding folder](https://github.com/Viren070/AIOStreams/tree/main/branding). The original studio icon collection is licensed under **CC BY-SA 3.0 US** as stated in [`LICENSE.txt`](LICENSE.txt). Changes to patterns, colours, and enabled states can be made directly in `nuvio-fusion-emblems.json` and then re-imported into Nuvio.
