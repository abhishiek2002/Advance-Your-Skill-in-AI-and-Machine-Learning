# 🖥️ How to Use GitHub Codespaces

---

## 🎯 Introduction

One of the cool features of **GitHub** is that it provides **Codespaces**. If you're not familiar with installing Python and its packages manually, no need to worry — Codespaces takes care of it for you. 🚀

Codespaces gives you a ready-to-use **cloud-based development environment** directly inside GitHub.

---

## 🛠️ Getting Started with Codespaces

### Step 1: Navigate to the Repository

* Go to the **GitHub project** for this course.
* Look for the **green `Code` button** and click on it.

### Step 2: Open Codespaces Tab

* A popup window will appear with **three tabs**.
* Select the **Codespaces** tab.

### Step 3: Create a Codespace

* At the top, you’ll see **Codespaces** with a **➕ (plus) button**.
* Click on it and select **Create a codespace on main**.

👉 Behind the scenes, GitHub provisions a **Linux environment** and installs **Python + all required packages**.

---

## ⚙️ Setup Process

* The setup may take **1–2 minutes**.
* You can check progress in the **Building section** for details.
* During setup, GitHub uses the **uv package manager** to install the environment.
* When the screen turns black and shows the **README**, setup is *still in progress*. Wait for the terminal at the bottom to finish running.

✅ Once the terminal finishes, your environment is ready.

---

## 📓 Working with Jupyter Notebooks

1. Open the **notebook file** (e.g., `ensembles.ipynb`).
2. Hide the terminal below (optional).
3. Select the **Kernel**:

   * Click on `Select Kernel` → `Python Environments` → choose **.venv** (the pre-configured environment).
   * Once selected, you’ll see `.venv` in the environment section.

### Running a Notebook Cell

* Click the **▶️ Play button** next to the cell, or
* Use the shortcut **Ctrl + Enter**.

💡 Example: Run the **Draw Data Cell** — if it executes successfully, everything is set up correctly.

---

## 📖 Quick Jupyter Tips

* **Create Text Cells**: You can create them, but not needed for this course.
* **Run Code Cells**: Use the play button or **Ctrl + Enter**.

---

## 💻 Running Locally (Alternative)

If you prefer running things locally:

1. Clone the repository.
2. Run:

   ```bash
   uv sync
   ```

   This will install all dependencies.

Then you’ll be ready to go locally, just like with Codespaces.

---

## 🚀 Key Takeaways

* **Codespaces** makes it super easy to set up a coding environment.
* No need to manually install Python or packages — everything is pre-configured.
* You can run Jupyter notebooks directly inside your browser.
* Alternatively, run locally using `uv sync`.

With Codespaces, you’re ready to dive into the course smoothly. 🎉
