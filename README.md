# Auto Annotation Engine with Florence 2

This repository contains an automated image annotation pipeline powered by **Florence 2**, a cutting-edge vision-language model developed by Microsoft. It enables rapid and scalable annotation of custom image datasets for object detection tasks, with outputs in **YOLO format** and additional human-readable labels.

---

## 📌 Features

* ⚡ **Fast auto-annotation** using Florence 2

* 🧠 Uses **vision-language understanding** (zero-shot or prompt-guided)

* 🖼️ Accepts any folder of input images

* 📝 Generates **YOLO-format `.txt` files** per image

* 🔤 Outputs readable `.txt` files with class names, bounding boxes, and confidence scores

* 🧪 **Batch processing** via PyTorch `DataLoader`

* 🧩 **Modular and extendable codebase**

---

## 📂 Project Structure

```bash
auto-annotation-engine/
├── data/
│ ├── images/ # Input images for annotation
│ └── labels/ # Output annotations (YOLO and readable)
├── outputs/
│ ├── yolo_labels/ # YOLO-format labels (class x_center y_center w h)
│ └── readable_labels/ # Human-friendly annotations (class name, score, bbox)
├── sample_results/
│ ├── example_input.jpg
│ └── example_annotated.jpg
└── README.md
```

---

## ⚙️ Setup Instructions

### ✅ Prerequisites

* Python $\geq$ 3.8

* Florence 2 model access (via HuggingFace Transformers or API key from Microsoft)

* GPU recommended (CUDA-compatible)

### 🛠 Installation

Clone the repository and install dependencies:

```bash
git clone [https://github.com/your-username/auto-annotation-engine.git](https://github.com/your-username/auto-annotation-engine.git)
cd auto-annotation-engine
```

---

## 🚀 Running the Annotation Pipeline

1. Place your images inside the `data/images/` directory.

2. Customize the list of target classes and thresholds in `annotate.py`.

3. Run the annotation script:

   ```bash
   python src/annotate.py
   ```

This will output YOLO-format labels in `outputs/yolo_labels/` and human-readable versions in `outputs/readable_labels/`.

---

## ✅ Supported Classes

Update the class map inside `annotate.py` as per your use case. For example:

```python
CLASS_MAP = {
    "car": 0,
    "bottle": 1,
    "dog": 2
}
```

You can change or extend this list as needed.

---

## 🖼️ Sample Results

![12](https://github.com/user-attachments/assets/c90e567f-05df-4278-bcaa-e3f13f09611f)

![08](https://github.com/user-attachments/assets/0a863855-e47c-4f49-adc9-9a2f0ef8a5b4)

![02](https://github.com/user-attachments/assets/00c5edc2-2c25-4082-96d5-6989457da291)

![04](https://github.com/user-attachments/assets/04af1efb-632a-466d-bbbe-fd85af1ced1a)

---

### 📥 Input Image

---

### 📤 Annotated Output

---

## 🧠 How It Works

1. The `ImageAnnotationDataset` loads images using a PyTorch-compatible format.

2. The `run_florence_annotation_on_dataloader` function batches and sends images to Florence 2.

3. Predictions are parsed and saved:

   * In YOLO format for training models.

   * In readable format for inspection or debugging.

4. Florence 2 leverages zero-shot vision-language modeling, optionally enhanced via prompts like "Detect cars, bottles, and dogs in this image."

---

## 📌 Configuration

You can tweak the following in `annotate.py`:

* Confidence threshold

* Prompt

* Batch size

* Save paths

---

## 🛠 TODO

* Add image segmentation support

* Convert annotations to COCO JSON format

* Add image annotation visualizer GUI

* Integrate model fine-tuning for specific domains

---

## 📜 License

This project is licensed under the MIT License — feel free to use, modify, and distribute with attribution.

---

## 🙋‍♀️ Questions or Feedback?

Feel free to reach out or open an issue.

📧 Email: niharika21545@iiitd.ac.in
🔗 LinkedIn: [[linkedin.com/in/your-profile]](https://www.linkedin.com/in/niharikasingh3632/)

---

## ⭐ If you found this useful...

Please consider ⭐ starring the repo and sharing it!
