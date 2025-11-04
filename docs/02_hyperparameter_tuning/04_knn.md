# 📍 k-NN Tuning

## 📘 Introduction: Guessing by Proximity

The **k-Nearest Neighbors (k-NN)** algorithm is fundamentally different from Decision Trees or Random Forests. It doesn't actually "train" a complex model; it is a **memory-based learner**.

* **The Idea:** To classify a new data point (a new person), k-NN simply looks at the people **closest** to it in the data and uses their information to make a guess.
* **Analogy:** Imagine a new person moves into a neighborhood. To guess their favorite sports team, you look at the **$k$ closest neighbors** and see which team they mostly support. The new person is assigned the majority vote.

**Tuning k-NN is primarily about answering two questions:**
1.  **How many neighbors ($k$) should we ask?**
2.  **Should all neighbors' opinions count equally?**

---

## ⚙️ Key Hyperparameters to Tune

### 1. `n_neighbors` (The Value of $k$)

This is the **most critical** hyperparameter for k-NN.

* **Analogy:** The **number of closest neighbors** you choose to ask for their opinion.
* **What it Controls:** The size of the "local neighborhood" used to make a prediction.
    * **Small $k$** (e.g., $k=1$): The prediction is based only on the single closest neighbor. This makes the model very sensitive to noise or weird, isolated data points, increasing the risk of **overfitting**.
    * **Large $k$** (e.g., $k=50$): The prediction is averaged over a very large area. This makes the model too smooth and ignores fine patterns, increasing the risk of **underfitting**.
* **Tuning Goal:** We search for the optimal $k$ that provides the best balance between responsiveness to local patterns and stability from large samples. A common starting point is often an odd number to avoid ties (e.g., $k=3$ or $k=5$).

### 2. `weights` (How Much Each Neighbor's Opinion Counts)

This parameter determines whether all the $k$ neighbors should have equal say in the final vote.

* **Analogy:** When you poll the neighbors, should the opinion of the neighbor **right next door** count more than the neighbor who lives three streets away?
* **What it Controls:**
    * **`weights = 'uniform'`:** **(Equal Weight)** All $k$ neighbors contribute equally to the final vote, regardless of how far away they are.
    * **`weights = 'distance'`:** **(Distance Weight)** Neighbors who are **closer** to the new data point have their vote weighted higher, while farther neighbors have less influence.
* **Tuning Goal:** 'Distance' weighting often provides better results because it makes intuitive sense: a closer neighbor's information is usually more relevant than a distant one. However, 'uniform' is simpler and a good baseline.

### 3. `metric` (How to Measure "Closeness")

This determines the mathematical rule used to calculate the distance between two data points.

* **Analogy:** How exactly do you measure "closeness"? Is it the straight line distance (as the crow flies), or the distance walked along the streets?
* **What it Controls:** The specific formula used to calculate the separation between two points.
    * **'Euclidean' (L2):** The standard "straight-line" distance. This is the most common default.
    * **'Manhattan' (L1):** The "city-block" distance, measuring distance by summing the horizontal and vertical paths (like navigating a grid).
* **Tuning Goal:** While 'Euclidean' is usually sufficient, trying 'Manhattan' can sometimes improve performance, especially when dealing with data that has many features or where diagonal paths aren't relevant.

---

## 💡 Summary and Strategy

| Hyperparameter | Analogy | Default/Common Values | Goal of Tuning |
| :--- | :--- | :--- | :--- |
| **`n_neighbors`** ($k$) | Number of neighbors to ask. | 3, 5, 7, 10 | Find the balance between **overfitting** (low $k$) and **underfitting** (high $k$). |
| **`weights`** | How much influence each neighbor has. | 'uniform' or 'distance' | Determine if closer neighbors should have a stronger vote. |
| **`metric`** | The formula for "closeness." | 'Euclidean' | Test different ways of measuring separation between data points. |

**Tuning Strategy:** k-NN is sensitive to the choice of $k$. You typically tune `n_neighbors` first, often within a range like 1 to 30, and then experiment with `weights='distance'` to see if it provides an improvement over the default 'uniform'.

