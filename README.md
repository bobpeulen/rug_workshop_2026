# rug_workshop_2026




## Conda steps

- Open a terminal
- Run the below commands step by step.


Establish and authenticate OCI Data Science Notebook with Object Storage. Note you might see a "UserWarning". You can ignore this warning.
```
odsc conda init -b oci_data_science_conda_bp -n fro8fl9kuqli -a resource_principal
```

Run the below commands in the terminal.
Note. The last command will take a few minutes to install all packages.
```
odsc conda install -s python_p311_any_x86_64_v3
```
```
conda activate /home/datascience/conda/python_p311_any_x86_64_v3
```
```
pip install diffusers[torch] transformers accelerate pillow oci oracle-ads
```

Run the below two commands. This will copy the Conda into a new environment named "sdxl" and publish it to Object Storage.
Note. Publishing the conda will take a few minutes. Wait for it to be completed. The output should end like image 1.
```
odsc conda clone -f python_p311_any_x86_64_v3 -e sdxl
```
```
odsc conda publish -s sdxlv3_0
```

*Image 1*
<img width="1510" height="303" alt="image" src="https://github.com/user-attachments/assets/74112d21-3f4c-4644-8c4d-c55e5b8b56dd" />


When curious, go back to Object Storage after completion of the above commands. You should see the conda environment.











x
