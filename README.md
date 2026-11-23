# Feature Engineering for AI Product Managers

Practise everything from the feature-engineering lecture: making raw data **model-ready** (gaps, words, rulers) and deciding **what a model may know** (leaks, the four tests, flags, feature specs). You fill in short blanks in prepared notebooks, run them cell by cell, and answer product questions. There are no functions to write and no long reading.

## Learning Objectives

By the end of this repository, you should be able to:

- Split first, then **fit** preparation steps on training data and only **transform** test and new data.
- Fill gaps on purpose (median, most frequent, "was missing" flag) and explain why **missing ≠ zero**.
- Encode categories without inventing an order (one-hot vs ordinal) and decide what happens to **unknown categories** in production.
- Choose a scaler (MinMax, Standard, Robust), and know that none of them removes outliers.
- Bundle the preparation into one recipe (`Pipeline` + `ColumnTransformer`).
- Spot a **leak** in a "too good" result, apply the **four tests** (available · same definition · allowed · useful), turn domain knowledge into **flags**, and write a **feature spec**.

## Learning Path

Work through the notebooks in order. Each takes about 45–60 minutes.

| File / Folder | Description |
|---|---|
| [**1 - Shape the Data**](1_shape_the_data.ipynb) | 🐧 PenguinTrack: split first, find gaps, imputation, one-hot vs ordinal, three scalers, log for skew. |
| [**2 - Snowman Exercise**](2_snowman_exercise.ipynb) | ⛄ SnowDay: plan per column, build `X_train_fe` (**M1**), new rows and the unknown "wrap" (**M2**), the same steps as one `Pipeline`. |
| [**3 - PM Feature Decisions**](3_pm_feature_decisions.ipynb) | ☕ BeanBox: Kai's AUC 1.00 model, hunt the leak, the four tests, yes/no flags, the final test with Nora's 100 calls, Belgium as an unknown country, your feature spec and recommendation. |

### How the notebooks work

| Marker | Meaning |
|---|---|
| ▶️ **Run** | Just run the cell. |
| ✏️ **Your turn** | Replace every `___` with your answer, then run. |
| ✅ **Check** | Tells you if you got it right, with a hint if not. |
| 🧠 **Think** | A PM question: write 1–3 sentences in the answer cell below it. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data/) | `penguins.csv`, `beanbox_subscribers.csv` (2,000 synthetic subscribers) and the data dictionary. The snowman data is typed into notebook 2. |
| [**Assets**](assets/) | Images used in the notebooks. |
| [**Solutions**](solutions/) | All three notebooks, solved, with outputs and sample answers. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

Use [uv](https://docs.astral.sh/uv/getting-started/installation/) 0.13.5 or newer and Python 3.13 (uv downloads it for you).

> [!NOTE]
> Text in angle brackets like `<repo-name>` is a **placeholder**. Replace it, including the `< >`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub, set yourself as the **Owner**, choose a name, disable **Include all branches**, and click **Create repository**.

### 2. Clone the Repository

```bash
git clone <copied-ssh-url>
```

### 3. Install the Dependencies

```bash
cd <repo-name>
uv sync
```

### 4. Open the Notebooks

```bash
code .
```

Open `1_shape_the_data.ipynb` and select the Python environment created by `uv sync` (`.venv`) as the kernel. Run the cells from top to bottom with `Shift + Enter`.

> [!TIP]
> If `uv sync` complains about the Python version, run `uv self update` and try again.

## References & Further Reading

- [scikit-learn: Preprocessing data](https://scikit-learn.org/stable/modules/preprocessing.html): imputation, encoding and scaling.
- [scikit-learn: Pipelines and composite estimators](https://scikit-learn.org/stable/modules/compose.html): how `ColumnTransformer` and `Pipeline` fit together.
- [scikit-learn: Common pitfalls (data leakage)](https://scikit-learn.org/stable/common_pitfalls.html): why preparation belongs inside the pipeline.
- [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/): the real dataset behind notebook 1.
