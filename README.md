### 📃️ Sphinix - Machine Learning Documentaion Projects

Sphinx is a documentation generator written and used by the Python community. It is written in Python and also used in other environments.

See more, [here](https://www.sphinx-doc.org/en/master/).

#### 📌 Dependencies

Create a `venv` and install dependencies:

```bash
    # Create environment
    $ python3 -m venv venv  

    # Activate environment
    $ source venv/bin/activate

    # Install dependencies
    $ pip install -r requirements.txt
``` 

Run a quickstart for your documentation:

```bash
    $ cd docs
    $ sphinx-quickstart
```

For see the first version of the documentation:

```bash
    # Inside docs/
    $ make html
```

Open the file `_build/html/index.html` to see a first version of the documentation.

For implement **autodoc sphinx**, change the `docs/conf.py` :

```python
    import sys
    import os

    # --- Omited Code ---

    sys.path.insert(0, os.path.abspath("../src"))
    extensions = ["sphinx.ext.autodoc"]

    # --- Omited Code ---
```

After this run :

```bash
    $ cd docs

    #  create reStructuredText for our Python modules
    $ sphinx-apidoc -o ./ ../src/

    # Rebuild to check the result:
    $ make html

    # Open the file _build/html/index.html to see the documentation.
```

Install a new theme with:

```bash
    $ pip install sphinx_rtd_theme

    # Then, change html_theme variable in the docs/config.py file from 
    # html_theme = "alabaster" to html_theme = "sphinx_rtd_theme".

    # Rebuild the project  
    $ make html
    # Open the file _build/html/index.html to see the documentation.
``` 

> :warning: **Possible error when run the make html command**
>   When run this command if you got a error like this: 
>  ```bash
>   checking consistency... /home/leticiacb/Documents/MachineLearningOPS/aula10/docs/modules.rst: WARNING: document isn't included in any toctree
>  ```
> Open file `docs/index.rst` and add this content :
> 
> ```bash
>  .. toctree::
>    :maxdepth: 2
>    :caption: Contents:
>
>  modules  # Add your modules.rst here without the .rst extension
>  ```
>
> Then run the "make html" again in see if this solves the problem.

<br>
@2024, Insper. 9° Semester,  Computer Engineering.
<br>

_Machine Learning Ops & Interviews Discipline_