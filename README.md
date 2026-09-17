# Studio Icons — Coloured

**Studio Icons — Coloured** is a Kodi resource add-on containing coloured PNG wordmarks and icons for film studios, television networks, distributors, production companies, game studios, and related media brands.

The package is intended for Kodi skins and add-ons that display a company or studio identity alongside media metadata. It installs as the `resource.images.studios.coloured` resource add-on and declares the Kodi image resource type `studios` in `addon.xml`.

## Contents

The `resources/` directory contains **7,434 PNG files**. The collection includes alternate names and regional variants where available. The root-level `studio-index.json` provides **7,091 normalized lookup entries** for client applications that need a stable key-to-filename mapping.

| Path | Purpose |
|---|---|
| `resources/` | Coloured PNG studio and media-brand images. |
| `studio-index.json` | Compact, machine-readable lookup index. |
| `addon.xml` | Kodi add-on manifest. |
| `info.xml` | Kodi resource metadata. |
| `icon.png` | Add-on icon. |
| `LICENSE.txt` | License notice for this collection. |

## Using the JSON index

`studio-index.json` has a simple structure. Each key is a normalized studio or brand name, and each value is the exact PNG filename in `resources/`.

```json
{
  "format": 1,
  "source": "Kodi resource.images.studios.coloured / Team Kodi",
  "license": "CC BY-SA 3.0 US",
  "count": 7091,
  "studios": {
    "marvelstudios": "Marvel Studios.png"
  }
}
```

A client can normalize a provider or studio name, find the corresponding value under `studios`, and build the local image path as `resources/<filename>`. Applications should handle a missing key gracefully because metadata providers may use an alias that is not yet indexed.

```python
from pathlib import Path
import json

root = Path("resource.images.studios.coloured")
index = json.loads((root / "studio-index.json").read_text(encoding="utf-8"))
filename = index["studios"].get("marvelstudios")
image_path = root / "resources" / filename if filename else None
```

The index is intentionally separate from the Kodi add-on manifest. It is useful to third-party clients, while Kodi skins can continue to resolve assets through their normal resource-image workflow.

## Kodi installation

Install the add-on from a Kodi repository that distributes `resource.images.studios.coloured`, or package this repository as a Kodi add-on ZIP. A compatible skin or add-on can then request studio artwork from the Kodi resource system.

> This repository is an artwork resource package. It does not fetch media metadata, identify studios, or modify a Kodi skin by itself.

## Attribution and license

This collection is distributed under the **Creative Commons Attribution-ShareAlike 3.0 United States** license. Reuse, modification, and redistribution must comply with the attribution and share-alike requirements in `LICENSE.txt`.[1]

The add-on metadata identifies the resource as **Studio Icons — Coloured** and credits **Team Kodi** as the provider.[2]

## Contributing

Contributions should preserve the existing PNG-based resource layout. When adding or renaming an image, update `studio-index.json` so applications using the compact lookup table can resolve the asset. Use normalized lowercase keys without spaces or punctuation, and keep filenames exactly as they appear under `resources/`.

Before opening a pull request, confirm that each index entry points to an existing file and that the JSON remains valid.

```bash
python3 - <<'PY'
from pathlib import Path
import json

root = Path(".")
index = json.loads((root / "studio-index.json").read_text(encoding="utf-8"))
missing = [
    filename for filename in index["studios"].values()
    if not (root / "resources" / filename).is_file()
]
assert not missing, f"Missing files: {missing[:10]}"
print(f"Validated {len(index['studios'])} indexed entries.")
PY
```

## References

[1]: https://creativecommons.org/licenses/by-sa/3.0/us/ "Creative Commons Attribution-ShareAlike 3.0 United States"
[2]: https://github.com/TrainAgain2/resource.images.studios.coloured/blob/master/addon.xml "Studio Icons — Coloured add-on manifest"
