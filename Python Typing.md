- Type hints were added in Python 3.5
- Not enforced by Python, but can be checked with linters and used by IDE for code completions
	- mypy is specially designed for this task, and will catch type errors before runtime
	- ```
	  pip install mypy
	  mypy path/to/code
	  ```
- Union = List of possible types when variable could be multiple things
- Optional = The given type or None
- ```python
  def f1(x: int, y: float, z: str) -> bool:
  	pass
      
  from pathlib import Path
  from typing import Union, Optional
  
  def f2(fpath: Union[str, Path], clean_up: Optional[bool]):
  	if clean_up is None:
      	pass
          
      if isinstance(fpath, str):
      	fpath = Path(fpath)
  ```