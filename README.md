# NLP Labs

Hands-on notebooks for the AIDAMS NLP course, grouped by lab delivery. Each lab directory is self-contained so you can focus on a single topic at a time.

## Project Structure

- `lab1/` – *NLP Introduction*: baseline preprocessing and classical models (`nlp_introduction.ipynb`).
- `lab1.1/` – *Maths & Optimisation Refresher*: supporting material for optimisation fundamentals (`Introduction_maths_optimisation.ipynb`).
- `lab2/` – *Optimisation in NLP*: optimisation-focused follow-up notebook (`maths_optimisation.ipynb`).
- `lab2.1/` – *Reconstruction Exercise*: complementary work for lab 2 (`reconstructed_notebook.ipynb`).
- `lab3/` – *Advanced Optimisation*: continued techniques used later in the course (`maths_optimisation.ipynb`).
- `lab3.1/` – *Transformer Training*: end-to-end transformer text classification workflow (`Training Transformer Models for Text Classification.ipynb`).
- `lab4/` – *Applied Analysis*: latest lab with its own `analysis.ipynb` notebook.

## Continuous Integration

Notebook execution is enforced by the **Notebook CI** workflow (`.github/workflows/run-notebooks.yml`). On every push to `main`/`master` and every pull request, GitHub Actions:

1. Checks out the repository and sets up Python 3.10.
2. Installs the shared dependencies defined in `requirements.txt` (which includes the Jupyter tooling required to execute notebooks).
3. Downloads the NLTK tokenizers (`punkt` and `punkt_tab`) so notebooks using `word_tokenize` run without manual setup.
4. Executes every tracked `.ipynb` file from a clean environment, ensuring the labs remain runnable end-to-end.

This guarantees that any change merged into the main branches keeps the teaching material executable for students.

> **Local tip:** If you execute the notebooks outside CI, run `python -m nltk.downloader punkt punkt_tab` once to mirror the CI environment.
