## Dependencies

```bash
micromamba create -n jupyterlab4 python=3.10 jupyterlab -c pytorch -c conda-forge -c nvidia -y
micromamba run -n jupyterlab4 pip install -r requirements.txt
```
