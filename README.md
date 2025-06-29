

# 🔍 Fingerprint Matching with OpenCV SIFT

This is a simple fingerprint matching program using **OpenCV's SIFT (Scale-Invariant Feature Transform)** and **FLANN-based matcher** to compare a sample fingerprint image against a collection of real fingerprint images and identify the best match based on feature similarity.

---

## 📁 Dataset

The program uses the **[SOCOFing dataset](https://www.kaggle.com/datasets/ruizgara/socofing)**, which contains:

* **Real** fingerprint images in the `/SOCOFing/Real/` directory.
* **Altered** fingerprint images in the `/SOCOFing/Altered/` directory.

Ensure the dataset is properly downloaded and extracted with the following directory structure:

```
SOCOFing/
├── Real/
│   ├── 1__M_Left_index_finger.BMP
│   ├── ...
├── Altered/
│   └── Altered-Hard/
│       ├── 150__M_Right_index_finger_Obl.BMP
│       ├── ...
```

---

## 📦 Dependencies

* Python 3.x
* OpenCV (with contrib modules)

You can install the required packages via:

```bash
pip install opencv-contrib-python
```

---

## 📖 How It Works

1. **Read the sample fingerprint image** (from `Altered-Hard/`).
2. **Iterate over a set of real fingerprint images** (first 1000 images from `Real/` directory).
3. For each image:

   * Detect keypoints and compute descriptors using **SIFT**.
   * Match descriptors using a **FLANN-based matcher**.
   * Apply the **Lowe's ratio test** to select good matches.
4. **Calculate the matching score** based on the ratio of good matches to the minimum number of keypoints in either image.
5. Keep track of the image with the **highest matching score**.
6. **Display the best match visually** by drawing the matching keypoints.

---

## 📊 Output

The program outputs:

* **The filename of the best matching fingerprint**
* **The matching score percentage**
* **A visual window displaying the matched keypoints**

Example:

```
best match: 002__M_Right_index_finger.BMP
score: 35.71
```

---

## 📸 Sample Result

A window displaying the sample and best matching fingerprint side-by-side with matched keypoints connected.

---

## 🚀 How to Run

Make sure your directory structure and dataset are in place, then simply run:

```bash
python fingerprint_matcher.py
```

---

## 📌 Notes

* This script uses a strict Lowe's ratio threshold (`0.1`) for selecting good matches — you might adjust this depending on your matching sensitivity requirements.
* Only the first 1000 images are processed for speed — you can increase or decrease this as needed.
* Ensure `opencv-contrib-python` is installed, as it includes the `SIFT_create()` function.

---

## 📚 Reference

* **SOCOFing Dataset**: [Kaggle Link](https://www.kaggle.com/datasets/ruizgara/socofing)
* **OpenCV SIFT Documentation**: [https://docs.opencv.org/master/da/df5/tutorial\_py\_sift\_intro.html](https://docs.opencv.org/master/da/df5/tutorial_py_sift_intro.html)

