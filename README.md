# Research Project Template

This repository serves as a template for organizing and managing research projects, from data acquisition to manuscript preparation and presentation. 

## Getting Started

To begin a new project using this template, follow these steps:

1. Create a new repository from this template:

    - Click the "Use this template" button (a green button near the top right).

    - Choose "Create a new repository."

    - Select an owner (your GitHub username or an Organization's name), provide a repository name (e.g., my-awesome-research-project), and choose its visibility (public or private).

    - Click "Create repository from template."

2. Clone your new repository:

    If you followed the OSC tutorials, see [this guide](https://lmu-osc.github.io/Collaborative-RStudio-GitHub/clone.html) for cloning via SSH within RStudio.

    As a general steo, you can clone the repository using either SSH or HTTPS in the command line as follows (please use one of the following methods):

    - **Using SSH**:
        ```bash
        git clone git@github.com:your-username/your-new-repository-name.git
        ```

    OR
    
    - **Using HTTPS**:
        ```bash
        git clone https://github.com/your-username/your-new-repository-name.git
        ```

    > **Note:**   `cd` is a command-line instruction used to change the current working directory, equivalent to double-clicking the folder in a file explorer.
    

3. Customize the README and adapt the directory structure to fit your project's needs:

    - Update this top-level README.md with a concise project title, description, and any initial setup instructions specific to your project.
    - Populate the `README.md` files within each subdirectory with relevant details as your project progresses. You can find a detailed guide on how to write a markdown file [here](https://www.markdownguide.org/basic-syntax/). 
    - Delete the example scripts and files from the template, such as `01_data/raw/example_data.csv`, `'02_analysis/01_data_cleaning.R`, etc., and replace them with your own data and scripts, as needed.

## Directory Structure

Below is an overview of the repository layout:

```
.
├── 01_data/                # All project data
│   ├── raw/                # Original, immutable data (do not modify)
│   ├── external/           # Data from outside sources (e.g., public datasets)
│   ├── processed/          # Cleaned/transformed data (outputs from scripts)
│   └── README.md           # Data sources, descriptions, processing steps
├── 02_analysis/            # Analysis scripts and utilities
│   ├── 01_data_cleaning.R  # Example: data cleaning script (R)
│   ├── 02_exploratory_analysis.py # Example: exploratory analysis (Python)
│   ├── 03_modeling.R       # Example: modeling script (R)
│   ├── utils/              # Reusable functions or modules
│   └── README.md           # Analysis workflow and script purposes
├── 03_manuscript/          # Manuscript drafts, figures, documents
│   └── README.md           # Track manuscript progress, submission plans, authors
├── 04_presentation/        # Materials for talks, posters, slides
│   └── README.md           # Summarize presentations (title, date, format)
├── 05_misc/                # Supplementary files (proposals, notes, etc.)
│   └── README.md           # Describe contents
└── README.md               # Project overview and setup instructions
```


## Good Practices

- **Reproducibility**:  
    - **Immutability of Raw Data**: Never modify files in `01_data/raw/`. Perform all cleaning and transformation programmatically or on copies, saving outputs to `01_data/processed/`.
    - **Environment Documentation**: Record your computational environment (e.g., `requirements.txt` for Python, `renv.lock` for R) to enable others to replicate your setup.

- **Version Control**:  
    - Commit changes frequently with clear, descriptive messages.
    - Use branches for new features or analyses.
    - **Use `.gitignore`**: Add files and directories to `.gitignore` to prevent tracking unnecessary or auto-generated content (e.g., intermediate results, logs, or large files). For example, you may choose not to track `01_data/processed/` since processed data should be reproducible by running scripts.

- **Clear Documentation**:  
    - Keep all `README.md` files up to date.
    - Comment code to explain critical steps and assumptions.

- **Sensitive Information**:  
    - Never commit sensitive data (credentials, API keys, personal info) to repositories
    - Add sensitive files to `.gitignore` before initial commits
    - Use environment variables or secrets management tools
    - Create template files (e.g., `.env.example`) showing required variable names
    - For sensitive datasets, document access procedures rather than including the data

- **Large Files**:  
    - Avoid committing very large files directly to Git. Use [Git LFS](https://git-lfs.github.com/), [git-annex](https://git-annex.branchable.com/), or research-specific tools such as [DataLad](https://www.datalad.org/) for managing large datasets or files, if appropriate for your workflow.
