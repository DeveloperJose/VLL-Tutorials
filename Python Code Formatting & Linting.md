- There are different tools, we will use the [ruff linter & formatter](https://docs.astral.sh/ruff/formatter/)
  id:: 666a089e-e67b-49fd-b023-502c6e6fe866
	- Very fast, used by FastAPI, Pandas, SciPy, Hugging Face
	- Can "lint" or check common code errors and "format" code to a consistent standard
	- ```sh
	  pip install ruff
	  
	  ruff check path/to/code
	  ruff format path/to/code
	  ```