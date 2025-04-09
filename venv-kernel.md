#### Create virtual environment
```
python -m venv [venv_name]
```

#### Activate virtual environment
- Linux:
  ```
  source [venv_name]/bin/activate
  ```
- Windows:
  ```
  [venv_name]\Scripts\activate
  ```

#### Deactivate venv
```
deactivate
```

#### See list of all venv
```
ls
```

#### Delete a venv
```
rm -rf [venv_name]
```

#### Install ipykernel
```
pip install ipykernel
```

### Create kernel
```
ipython kernel install --user --name=[kernel_name]
```

