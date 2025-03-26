# Ultralytics Zed Snippets
Ultralytics snippets for Zed IDE.
- This project is an adaptation of the VSCode plugin called [ultralytics-snippets](https://github.com/Burhan-Q/ultralytics-snippets) created by [Burhan-Q](https://github.com/Burhan-Q).

## Installation

### Method 1

1. Go to Extensions menu in Zed IDE
2. Search for "ultralytics-zed-snippets"
3. Click "Install"

### Method 2
1. Clone this repo:
```
git clone https://github.com/ayberkgezer/ultralytics-zed-snippets.git
```
2. Go to Extensions menu in Zed IDE
3. Click "Install Dev Extension"
4. Select the folder you cloned

## Usage

Start typing `ultra.` in a Python file to see the available snippets. Snippets are organized into categories:

- `ultra.yolo-*`: YOLO model operations
- `ultra.sam-*`: SAM model operations
- `ultra.util-*`: Utility functions
- `ultra.result-*`: Working with results
- `ultra.kwargs-*`: Method arguments
- `ultra.example-*`: Complete examples
- `ultra.import-*`: Import statements

## Import

Import snippets are for common objects that would be imported from the Ultralytics library.

| Alias                       | Description                                                                                  |
| --------------------------- | -------------------------------------------------------------------------------------------- |
| `ultra.import-model`        | Add line to import Ultralytics YOLO                                                          |
| `ultra.import-assets`       | Import Ultralytics ASSETS directory constant.                                                |
| `ultra.import-results`      | Import Ultralytics Results class (usually for type hinting).                                 |
| `ultra.import-annotator`    | Import Ultralytics auto_annotate function.                                                   |
| `ultra.import-coco2yolo`    | Import Ultralytics function to convert annotations from COCO to YOLO format.                 |
| `ultra.import-bbox2seg`     | Import Ultralytics function to convert horizontal bounding boxes to segmentation contours.   |
| `ultra.import-seg2bbox`     | Import Ultralytics function to convert segmentation contours into horizontal bounding boxes. |
| `ultra.import-box-convert`  | Import Ultralytics function for converting bounding box coordinates.                         |
| `ultra.import-formats`      | Import Ultralytics supported file formats constant.                                          |
| `ultra.import-task-result`  | Import task-based results class (generally helpful for type hinting).                        |


## Results

These snippets will provide shortcuts for working with `ultralytics.engine.results.Results` objects returned from model inference. See the [Working with Results][pred results] of the documentation and the [Results class] reference page for more information.

| Alias                        | Description                                                                                                        |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `ultra.result-class-str`     | Convert class indices to class string names for a single image result.                                             |
| `ultra.result-data`          | Get result data array of detections from a single image result.                                                    |
| `ultra.result-loop`          | Iterate prediction results from an Ultralytics model.                                                              |
| `ultra.result-box-xyxy`      | Get pixel-value `(x1, y1, x2, y2)` bounding box coordinates from a single image result.                            |
| `ultra.result-box-xywh`      | Get pixel-value `(x-center, y-center, w, h)` bounding box coordinates from a single image result.                  |
| `ultra.result-mask-binary`   | Get binary segmentation masks from a single image result. NOTE: `[N, H, W]` shape, with inference H, W dimensions. |
| `ultra.result-mask-contours` | Get segmentation contours with pixel value `xy` or normalized `xyn` coordinates.                                   |
| `ultra.result-obb-xywhr`     | Get OBB rotated bounding boxes in pixel value `[x, y, w, h, r]` coordinates as torch.Tensor array.                 |
| `ultra.result-orig-image`    | Get original image from a single image result.                                                                     |
| `ultra.result-filter-class`  | Filter prediction results by class ID. Using `classes` keyword argument for prediction should be preferred.        |


## Models

Shortcuts for initializing pretrained [Ultralytics models][models], like [YOLOv8].

| Alias                    | Description                                                  | Reference                                             |
| ------------------------ | ------------------------------------------------------------ | ----------------------------------------------------- |
| `ultra.yolo-model`       | Shortcut to initialize YOLO model.                           | [YOLOv5], [YOLOv8], [YOLOv9], [YOLOv10], [YOLO-World] |
| `ultra.yolo-export`      | Shortcut to export YOLO model weights.                       | [Model Export]                                        |
| `ultra.sam-model`        | Shortcut to initialize SAM.                                  | [SAM]                                                 |
| `ultra.mobileam-model`   | Shortcut to initialize MobileSAM.                            | [Mobile SAM]                                          |
| `ultra.fastam-model`     | Shortcut to initialize FastSAM.                              | [FastSAM]                                             |
| `ultra.nas-model`        | Shortcut to initialize YOLO-NAS model.                       | [YOLO-NAS]                                            |
| `ultra.rtdetr-model`     | Shortcut to initialize RTDETR model.                         | [RTDETR]                                              |
| `ultra.yolo-world-model` | Shortcut to initialize YOLO-world model, with class prompts. | [YOLO-World]                                          |
| `ultra.sam2-bboxes`      | Shortcut to initialize YOLO-World model with text prompts.   | [SAM2]                                                |
| `ultra.sam2-points`      | Shortcut to initialize YOLO-World model with text prompts.   | [SAM2]                                                |


## Utilities

| Alias                       | Description                                                                    | Reference                              |
| --------------------------- | ------------------------------------------------------------------------------ | -------------------------------------- |
| `ultra.util-auto-annotate`  | Use Ultralytics auto_annotate function to generate annotations.                | [`auto_annotator` fucntion][auto ann]  |
| `ultra.util-annotator`      | Use Ultralytics Annotator class to draw box annotations                        | [`Annotator` class][ann]               |
| `ultra.util-make-divisible` | Use Ultralytics make_divisible function to make a number divisible by another. | [`make_divisible` function][divisible] |
| `ultra.util-callback`       | Shortcut for adding custom model callback for a defined function.              | [`callbacks`][callbacks]               |


## Examples

The Example snippets are more "complete" blocks of code that can be used for boilerplate demonstrations.

| Prefix                               | Description                                                                                                     |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| `ultra.example-predict-filter-class` | Ultralytics basic YOLO object detection predict with filtered classes example.                                  |
| `ultra.example-result-filter-class`  | Filter prediction results by class ID. Using "classes" keyword argument for prediction should be preferred.     |
| `ultra.example-yolo-predict`         | Setup Ultralytics YOLO to perform predict (simple).                                                             |
| `ultra.example-yolo-val`             | Setup Ultralytics YOLO to perform validation (simple).                                                          |
| `ultra.example-yolo-train`           | Setup Ultralytics YOLO to perform training (simple).                                                            |
| `ultra.example-yolo-predict-kwords`  | Setup Ultralytics YOLO to perform inference, show **all** inference keyword arguments and their default values. |
| `ultra.example-yolo-train-kwords`    | Setup Ultralytics YOLO for training, with **all** keyword arguments and their default values.                   |
| `ultra.example-sam-predict`          | Setup Ultralytics SAM to perform inference (simple).                                                            |
| `ultra.example-sam2`                 | Example showing use of SAM2 with bounding box and point prompts.                                                |
| `ultra.example-mobile-sam-predict`   | Setup Ultralytics MobileSAM to perform inference (simple).                                                      |
| `ultra.example-fast-sam-predict`     | Setup Ultralytics FastSAM to perform inference (simple).                                                        |
| `ultra.example-nas-predict`          | Setup Ultralytics NAS to perform inference (simple).                                                            |
| `ultra.example-rtdetr-predict`       | Setup Ultralytics RT-DETR to perform inference (simple).                                                        |
| `ultra.example-callback`             | Example showing how to add a custom callback function.                                                          |
| `ultra.example-track-loop-persist`   | Example of how to open video, loop frames, and maintain tracked object IDs.                                     |
| `ultra.example-track-kwords`         | Example showing all keyword arguments available for track mode.                                                 |

## KWARGS

Use these to insert the various model methods defined in [modes] with all keyword arguments, default values, and commented descriptions quickly into your code. Includes `model` as default variable, but is an editable field accessible using tab stops.

| Prefix                 | Description                                                                              | Reference  |
| ---------------------- | ---------------------------------------------------------------------------------------- | ---------- |
| `ultra.kwargs-predict` | Snippet using model `predict` method, including all keyword arguments and defaults.      | [predict]  |
| `ultra.kwargs-train`   | Snippet using model `train` method, including all keyword arguments and defaults.        | [train]    |
| `ultra.kwargs-track`   | Snippet using model `track` method, including all keyword arguments and defaults.        | [track]    |
| `ultra.kwargs-val`     | Snippet using model `val` method, including all keyword arguments and defaults.          | [val]      |


## Credits and Attribution

This project is an adaptation of the VSCode plugin called [ultralytics-snippets](https://github.com/Burhan-Q/ultralytics-snippets) created by [Burhan-Q](https://github.com/Burhan-Q). The original project is licensed under AGPL-3.0. All content structure, descriptions, and snippet design have been adapted for Zed IDE from the original VSCode extension. Full credit for the original concept, structure, and content goes to the original author.

Original source: [Github - ultralytics-snippets](https://github.com/Burhan-Q/ultralytics-snippets)
