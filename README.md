# University of Groningen - Workshop Steps - 2026

Title: Self-Hosting Stable Diffusion XL with OCI Data Science



## Creating and publishing a new Conda Environment.

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

When curious, go back to Object Storage after completion of the above commands. You should see the conda environment like in the below screenshot.

 
 *Image 2*
 <img width="698" height="587" alt="image" src="https://github.com/user-attachments/assets/ca8d2c38-e186-4b86-9c75-1f8f17534157" />

## Open the Notebook and Run the cells

1. Clone this repository
.. Git clone


2. Open the notebook and select the just created Conda environment. See image 3.
   ```
   Python[Conda env:sdxlv3_0]
   ```

*Image 3*
 <img width="432" height="166" alt="image" src="https://github.com/user-attachments/assets/7b628443-2d56-4cd2-89b9-5b5cb3b89719" />
















x
