# Intel Extension for TensorFlow Getting Started Sample
This code sample will guide users how to run a tensorflow inference workload on both GPU and CPU by using Intel® AI Tools and also analyze the GPU and CPU usage via oneDNN verbose logs

## Purpose
  - Guide users how to use different conda environments in Intel® AI Tools to run TensorFlow workloads on both CPU and GPU
  - Guide users how to validate the GPU or CPU usages for TensorFlow workloads on Intel CPU or GPU
 

## Key implementation details
1. leverage the [resnet50 inference sample](https://github.com/intel/intel-extension-for-tensorflow/tree/main/examples/infer_resnet50) from intel-extension-for-tensorflow
2. use the resnet50v1.5 pretrained model from TensorFlow Hub
3. infernece with images in intel caffe github
4. guide users how to use different conda environment to run on Intel CPU and GPU
5. analyze oneDNN verbose logs to validate GPU or CPU usage  

## Pre-requirements (Local or Remote Host Installation)

TensorFlow* is ready for use once you finish the Intel® AI Tools installation and have run the post installation script.

TensorFlow* is ready for use once you finish the Intel AI Tools installation. You can refer to the oneAPI [product page](https://software.intel.com/en-us/oneapi) for tools installation and the *[Get Started with the Intel® AI Tools for Linux*](https://software.intel.com/en-us/get-started-with-intel-oneapi-linux-get-started-with-the-intel-ai-analytics-toolkit)* for post-installation steps and scripts.

## Environment Setup
This sample requires two additional pip packages: tensorflow_hub and ipykerenl.  
Therefore users need to clone the tensorflow conda environment into users' home folder and install those additional packages accordingly.   
Please follow bellow steps to setup GPU environment.  

1. Source oneAPI environment variables:  ``` $source $HOME/intel/oneapi/intelpython/bin/activate  ```
2. Create conda env:  ```$conda create --name user-tensorflow-gpu --clone tensorflow-gpu ```
3. Activate the created conda env:  ```$source activate user-tensorflow-gpu ```
4. Install the required packages:  ```(user-tensorflow-gpu) $pip install -r requirements.txt ```
5. Deactivate conda env:  ```(user-tensorflow-gpu)$conda deactivate ```
6. Register the kernel to Jupyter NB: ``` $~/.conda/envs/user-tensorflow-gpu/bin/python  -m ipykernel install --user --name=user-tensorflow-gpu ```  

Once users finish GPU environment setup, please do the same steps but remove "-gpu" from above steps. 
In the end, you will have two new conda environments which are user-tensorflow-gpu and user-tensorflow

## How to Build and Run

You can run the Jupyter notebook with the sample code on your local
server or download the sample code from the notebook as a Python file and run it locally.


### Run the Sample in Jupyter Notebook<a name="run-as-jupyter-notebook"></a>

To open the Jupyter notebook on your local server:

1. Start the Jupyter notebook server. ``` jupyter notebook --ip=0.0.0.0   ```
   
2. Open the ``ResNet50_Inference.ipynb`` file in the Notebook Dashboard.  

3. Select the related jupyter kernel. In this example, select 'Kernel' -> 'Change kernel' -> user-tensorflow-gpu for GPU run as the first step.  
   
4. Run the cells in the Jupyter notebook sequentially by clicking the **Run** button.  

6. select user-tensorflow jupyter kernel and run again from beginning for CPU run.  

---
**NOTE**

In the jupyter page, be sure to select the correct kernel. In this example, select 'Kernel' -> 'Change kernel' -> user-tensorflow-gpu or user-tensorflow.

---

### Troubleshooting
If an error occurs, troubleshoot the problem using the Diagnostics Utility for Intel® oneAPI Toolkits.
[Learn more](https://software.intel.com/content/www/us/en/develop/documentation/diagnostic-utility-user-guide/top.html)

## License
Code samples are licensed under the MIT license. See
[License.txt](https://github.com/oneapi-src/oneAPI-samples/blob/master/License.txt) for details.

Third party program Licenses can be found here: [third-party-programs.txt](https://github.com/oneapi-src/oneAPI-samples/blob/master/third-party-programs.txt)

After learning how to use the extensions for Intel oneAPI Toolkits, return to this readme for instructions on how to build and run a sample.
