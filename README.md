# Architecture
![ELT-Architecture](architecture/ELT.png)

# How to run it ?
## Pre-requisites
1. Create `virtual environment`
```
# create the environment
python -m venv <venv-name>

# activate the environment
<venv-name>\Scripts\activate # for Windows
source <name-venv>/bin/activate # for Linux or Mac
```

2. If you run on `linux` or `Mac`, you should follow the steps below
```
sudo apt-get install git libpq-dev python-dev python3-pip
sudo apt-get remove python-cffi
sudo pip install --upgrade cffi
pip install cryptography~=3.4
```

3. `libraries` installation
```
pip install -r requirements/requirements.txt
```

4. `dbt` installation
```
python -m pip install -r requirements/dbt-installation.txt
```

5. If you are done, you can set up the `profiles.yml` file because in contains credentials for connections.
You can find it in [About Profiles](https://docs.getdbt.com/docs/core/connect-data-platform/profiles.yml)

6. Test connection with `dbt`
```
dbt debug --profiles-dir <Dest path file profiles.yml> --project-dir dbt_project
```

7. Run `dbt`
```
dbt run --profiles-dir <Dest path file profiles.yml> --project-dir dbt_project
```

8. Generate `dbt` documentation
```
dbt docs generate --profiles-dir <Dest path file profiles.yml> --project-dir dbt_project
```

9. Connect to local server `dbt`
```
dbt docs serve --profiles-dir <Dest path file profiles.yml> --project-dir dbt_project
```