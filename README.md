# rug_workshop_2026




## Conda steps

- Open a terminal
- Run the below commands step by step.


Establish and authenticate OCI Data Science Notebook with Object Storage
```
odsc conda init -b oci_data_science_conda_bp -n fro8fl9kuqli -a resource_principal
```

Run the below commands in the terminal.
Note. The last command will take a few minutes to install all packages.
```
odsc conda install -s python_p311_any_x86_64_v3
conda activate /home/datascience/conda/python_p311_any_x86_64_v3
pip install diffusers[torch] transformers accelerate pillow oci oracle-ads
```

Run the below two commands. This will copy the Conda into a new environment named "sdxl" and publish it to Object Storage.
```
odsc conda clone -f python_p311_any_x86_64_v3 -e sdxl
odsc conda publish -s sdxlv2_0
```

When curious, go back to Object Storage after completion of the above commands. You should see the conda environment.
