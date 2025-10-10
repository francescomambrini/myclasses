🐍 Python Setup Guide for the class

We’ll all use the **same Python environment** to avoid “it works on my computer” problems. Please follow the steps below.

## 1. Install Anaconda (or Miniforge)

- If you’ve **never used Python before**:  
  👉 [Download Anaconda](https://www.anaconda.com/download) (choose the version for your OS).  
  - Windows & Mac Intel: installer is straightforward.  
  - Mac M1/M2 (Apple Silicon): it is often recommended to use **Miniforge** → [Miniforge download](https://github.com/conda-forge/miniforge).  

- If you’re an **expert user** and already have conda/miniforge installed → skip this step, but make sure your conda is up to date:

```bash
  conda update -n base -c defaults conda
```
## 2. Download the environment file

I will provide you with a file called **`environment.yml`**. Save it to your computer

## 3. Create the environment

Open a terminal (or Anaconda Prompt on Windows) and run:

```bash
conda env create -f environment.yml
```

This will create an environment called **`digitools`**.

## 4. Activate the environment

Every time you want to work on class material, run:

```bash
conda activate digitools
```

## 5. Register the environment as a Jupyter kernel

We will **not** install Jupyter in every environment.  
Instead, we’ll install it once in the base environment, and then register `digitools` as a kernel.

While `digitools` is activated, run:

```bash
python -m ipykernel install --user --name digitools --display-name "Python (digitools)"

```

## 6. Start Jupyter

Now start Jupyter from the **base** environment:

```bash
jupyter notebook
```

## 7. If something goes wrong

- To delete and rebuild the environment:

```bash
conda env remove -n digitools
conda env create -f environment.yml
```

- If Jupyter doesn’t see the kernel, repeat step 5.
## 8. Alternative (for experts 🚀)

If you prefer **not** to use `conda`, you can install packages directly with `pip` (and use [venv](https://docs.python.org/3/library/venv.html) to manage your environment):

```bash
pip install -r requirements.txt
```

⚠️ Be aware: results may differ slightly from the conda setup, so class support will focus on the conda environment.

---

✅ That’s it! Once set up, you’re ready to run all class exercises.


## Appendix: requirements

- This is the content of `environment.yml`:

```yaml
name: digitools
channels:
  - conda-forge
  - defaults
dependencies:
  - python>=3.9
  - nltk
  - pandas
  - scipy
  - seaborn
  - scikit-learn
```

- This is the content of `requirements.txt`

```txt
nltk
pandas
scipy
seaborn
scikit-learn
```

#digitools 
