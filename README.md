# **Point Cloud Registration using Iterative Closest Point (ICP) - Open3D**

This project implements **Iterative Closest Point (ICP)** to align two 3D point clouds using **Open3D**. The algorithm minimizes the difference between the source and target point clouds through an iterative nearest-neighbor matching process.

## **Overview**
- The script takes **two point clouds** and aligns them using **ICP**.
- It finds the **best transformation matrix** (rotation + translation) to minimize alignment error.
- The process iterates until the error **converges** or reaches the threshold.

---

## **Installation**
Ensure you have Python installed along with the required dependencies:

```bash
pip install open3d numpy
```

---

## **Usage**
1. Run the script:

   ```bash
   python icp_registration.py
   ```

2. The algorithm will:
   - Load demo point clouds.
   - Apply **ICP registration** to align them.
   - Display the **aligned point clouds**.
   - Print the final transformation matrix.

---

## **How It Works**
1. **Load Data**: Reads two point clouds (source & target).
2. **Pre-processing**:
   - Initializes a transformation matrix.
   - Iteratively refines alignment.
3. **ICP Algorithm Steps**:
   - Finds **nearest neighbors** using **KDTree**.
   - Computes **centroids** of matched points.
   - Uses **Singular Value Decomposition (SVD)** to estimate the best transformation.
   - Applies the transformation and repeats until **error convergence**.
4. **Visualization**:
   - Displays aligned point clouds in **Open3D**.

---

## **Results**
- The **final transformation matrix** is printed.
- The **aligned point clouds** are displayed with:
  - **Red**: Source point cloud.
  - **Green**: Target point cloud.

---

## **Potential Improvements**
✅ Use Open3D’s **built-in ICP function** for performance gains.  
✅ Implement **downsampling** for large point clouds.  
✅ Add **outlier filtering** for noisy datasets.  
✅ Test with **real-world 3D scans**.  
