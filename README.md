# Apple Rotation and Surface Presentation on a Screw Conveyor

Annotated image dataset accompanying the study **Quantitative Evaluation of Apple Rotation and Surface Presentation on a Screw Conveyor for Full-Surface Imaging**.

This dataset contains **1,421 annotated images** of apples painted with patches in **17 distinct colors**. The painted regions serve as visual markers for studying apple rotation and surface presentation. Segmenting and tracking these regions across image sequences supports analysis of how different parts of the apple surface become visible during rotation.

## Download

**[Access the annotated dataset on Zenodo](https://zenodo.org/records/23890322)**

- **Compressed archive:** 7.39 GB
- **Approximate uncompressed size:** 28 GB
- **Included data:** BMP images, original LabelMe JSON annotations, and converted YOLO-compatible TXT annotations

This release provides the annotated image collection prepared for training color-region segmentation models.

## Dataset Summary

| Attribute | Description |
| --- | --- |
| Annotated images | 1,421 |
| Painted color categories | 17 |
| Image format | BMP (`.bmp`) |
| Image dimensions | 1600 × 2848 pixels (width × height), consistent across all images |
| BMP bit depth | 32 bits per pixel |
| Runs per apple at each speed | Two: one in lane 1 and one in lane 2 |
| Annotation software | LabelMe |
| Original annotations | Polygon annotations in JSON format |
| Converted annotations | YOLO-compatible TXT files |
| Predefined training/validation/test split | None |
| Main application | Color-region segmentation to support apple rotation and surface presentation analysis |

## Dataset Organization

The downloaded data are organized into three directories:

| Directory | Contents | Number of files |
| --- | --- | ---: |
| `labeled data/` | BMP images corresponding to the annotations | 1,421 |
| `json/` | Original LabelMe polygon annotations | 1,421 |
| `txt/` | YOLO-compatible annotations converted from the JSON files | 1,421 |

Images, JSON annotations, and TXT annotations correspond **one-to-one**. Each image has an associated JSON annotation file and a corresponding TXT annotation file. The JSON and TXT files represent annotations for the same images.

## Annotations

### LabelMe JSON

The visible painted color regions were annotated using polygons in LabelMe. Each polygon delineates the boundary of a color region and is associated with its color category. The original annotations are provided in the `json/` directory.

### YOLO TXT

The `txt/` directory contains annotations converted from the original JSON files for YOLO training workflows. Each TXT file corresponds to the same image as its associated JSON file.

## Acquisition Runs and File Naming

Each apple was tested twice **at each speed**, once in lane 1 and once in lane 2. A test identifier denotes an experimental run, while a frame index identifies an image within that run. Multiple runs can therefore contain observations of the same physical apple.

Filenames identify the experimental run and the image index within that run. Some filenames also include a prefix describing acquisition conditions. For example:

```text
V4S2-HFYU_test-7_134.bmp
```

| Component | Meaning |
| --- | --- |
| `V4` | Variety identifier |
| `S2` | Operating speed code |
| `test-7` | Experimental run identifier 7; in this example, the third apple imaged in lane 2 |
| `134` | The 134th image within the indicated run |
| `.bmp` | BMP image format |

The prefix `V4S2-HFYU_` is not present in all filenames. When the prefix is omitted, the trailing test identifier and frame index retain the same meanings. Some filenames also omit the hyphen after `test`, as in `test1_1.bmp`.

Preserve the correspondence between images and their JSON and TXT annotations when reorganizing files or constructing data partitions.

## Usage

1. Download the annotated dataset from the [Zenodo record](https://zenodo.org/records/23890322) and extract the archive.
2. Use the BMP images with the annotation format required by your workflow: original LabelMe JSON files or converted YOLO-compatible TXT files.
3. Create training, validation, and test partitions appropriate to your experiments. **No predefined split is provided.**

## Complete Dataset Access

The public release contains the annotated training subset. The **complete dataset is approximately 2 TB** in size. Researchers who need access to the complete dataset may **contact the authors** to request access.

## Related Study and Citation

**Quantitative Evaluation of Apple Rotation and Surface Presentation on a Screw Conveyor for Full-Surface Imaging**

If you use these data in your research, please cite the dataset through its [Zenodo record](https://zenodo.org/records/23890322).
