- Some tasks like preprocessing images benefit from parallelizing a function to run across multiple CPUs and cores
- This is an optimization to do AFTER you create a function or program that takes a long time to run
- If you can set-up a function that handles work for one item, you can easily parallelize in a few lines
- MUST use **__main__** function for it to always work properly
- There's a lot of tutorials for all multiprocessing functions, "map" is just one of them
- ```python
  from multiprocessing import Pool
  - def do_work(data):
  pass
  - def main():
  cpu_cores = 4
  all_work = [["A", 5], ["B", 2], ["C", 1]]
  with Pool(cpu_cores) as p:
    p.map(do_work, all_work)
  - if __name__ == "__main__":
  main()
  ```