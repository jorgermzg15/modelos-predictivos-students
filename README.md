# Linear Regression Intro — Students

Hands-on lab template for the Linear Regression class. Follow along with the instructor and complete the empty cells in each notebook.

## Project Structure

**Session 1 — Linear regression**
- `01-regresion-lineal/fundamentos.ipynb`: Theory — OLS, coefficients and assumptions
- `01-regresion-lineal/caso_mpg.ipynb`: 🎯 Hands-on lab — predict fuel efficiency (MPG): EDA, simple and multiple regression, VIF + p-values and RFECV

**Session 2 — Logistic regression**
- `02-regresion-logistica/fundamentos.ipynb`: Theory — sigmoid, log-odds and maximum likelihood
- `02-regresion-logistica/caso_titanic.ipynb`: 🎯 Hands-on lab — who survived the Titanic: imputation, odds ratios, confusion matrix, precision/recall, decision threshold and ROC/AUC
- `02-regresion-logistica/slides/`: Logistic regression infographic

**Session 3 — Decision trees**
- `03-arboles/fundamentos.ipynb`: Theory — binary splits, impurity, pruning, feature importance
- `03-arboles/caso_mpg.ipynb`: 🎯 Regression tree on the MPG case
- `03-arboles/caso_titanic.ipynb`: 🎯 Classification tree on the titanic case

**Session 4 — KNN** (asynchronous)
- `04-knn/fundamentos.ipynb`: Theory — euclidean distance, why scaling is mandatory, the role of k
- `04-knn/caso_mpg.ipynb`: 🎯 KNN regression on the MPG case
- `04-knn/caso_titanic.ipynb`: 🎯 KNN classification plus the course wrap-up

From session 3 on, the data arrives already prepared through `cargar_*()` / `preparar_*()`, with the same
split you built by hand in sessions 1 and 2, so results stay comparable across models.

Each session gets its own numbered folder; new ones appear as the course advances.

**Extra practice**
- `extra/diamonds/regresion_lineal.ipynb`: Predict diamond prices
- `extra/california/seleccion_vif_pvalues.ipynb`: Variable selection with VIF and p-values (California Housing)

**Environment**
- `pyproject.toml` / `uv.lock`: Project dependencies and the exact pinned versions
- `.python-version`: Exact Python version used everywhere
- `.devcontainer/`: GitHub Codespaces / Dev Container configuration

Each notebook starts with a "Preparación" section with helper functions: run those cells once and then just call the functions.

The SQLite databases are downloaded automatically by the notebooks (they are not versioned).

## Tools and Technologies

- Python 3.14 (exact version in `.python-version`)
- [uv](https://docs.astral.sh/uv/) to manage Python and dependencies
- Jupyter Notebooks (VS Code + Jupyter extension)
- pandas, NumPy, SciPy, scikit-learn, statsmodels, Plotly

## Environment

The local environment and GitHub Codespaces are built from the same files, so they are identical:

- `.python-version` pins the exact Python version (installed by uv, same build on every machine).
- `uv.lock` pins the exact version of every package.
- Codespaces runs `uv sync --frozen` when the container is created, which is the same command used locally.

### Option A: GitHub Codespaces (recommended)

Click **Code → Codespaces → Create codespace on main**. When the setup finishes, open any notebook and select the `.venv` kernel.

### Option B: Local

1. Install uv:
   ```bash
   # macOS
   brew install uv

   # Windows (PowerShell)
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

2. Clone this repository and create the environment:
   ```bash
   git clone https://github.com/jorgermzg15/modelos-predictivos-students.git
   cd modelos-predictivos-students
   uv sync --frozen
   ```

3. Open the folder in VS Code and select the `.venv` interpreter/kernel in the notebooks.

### Updating dependencies (instructor)

```bash
uv lock --upgrade   # resolve the newest compatible versions
uv sync --frozen    # apply them locally
```

Commit `uv.lock` (and `.python-version` if you change it). Codespaces will pick up the same versions on the next rebuild.

## Troubleshooting

1. Make sure the notebook kernel is the project's `.venv` (not a Conda/Anaconda environment).
2. If the environment gets out of sync, recreate it:
   ```bash
   rm -rf .venv
   uv sync --frozen
   ```
3. In Codespaces, if something breaks after changing `.devcontainer/`, run **Codespaces: Rebuild Container** from the command palette.

## For Students

1. Follow the environment instructions carefully
2. Execute the notebook cells in order
3. Complete the cells marked with ✍️ following the hints in each one
4. Experiment with the code and parameters to deepen your understanding

## License

This project is available for educational purposes. Feel free to use and learn from it!

## Database Credits

The SQLite databases used in this project are sourced from the [SQLite Databases for Learning Data Science](https://github.com/davidjamesknight/SQLite_databases_for_learning_data_science) repository by David James Knight.
