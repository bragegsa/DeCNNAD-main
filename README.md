## Background

This is a realization of the Hyperspectral Anomaly detector proposed in the article: "Hyperspectral Anomaly Detection via DeepPlug-and-Play DenoisingCNN Regularization".

** I have no rights to the code. It is written by X. Fu, S. Jia, L. Zhuang, M. Xu, J. Zhou and Q. Li. **

## How to run

### Cuda
* Check if your GPU supports CUDA capability by going to: chrome://gpu/
    * If so, download CUDA toolkit at: https://developer.nvidia.com/cuda-toolkit

### Matlab

1. Clone the repository
2. Download Matlab
3. Download ADD-on: MatConvNet
4. Download Visual Studio C++ Compiler

### Running Main_demo.m

1. Change line 426 in "vl_compilenn.m" to have the correct path to your cl.exe file.
    * Example: 
            
            cl_path = 'C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.29.30133\bin\Hostx64\arm64';
2. Compiling the MatCocNet Add-on
    1. In the Matlab terminal you will have to change the C++ compiler to the Visual Studio compiler. Write the following and choose the Visual Studio C and C++ compiler:

            mex -setup C

            mex -setup C++
    2. Then write the following into the terminal:
        
            vl_compilenn('enableGpu', true)

            vl_compilenn('EnableImreadJpeg', false) (Only for testing if the one above does not work)
    3. You can then setup the Add-on by running:
            vl_vl_setupnn
3. You are then ready to run Main_demo.m

### Problems?

More documentation can be found here:

* Installation guide of MatConvNet: https://www.vlfeat.org/matconvnet/install/
* Compilation guide of MatConvNet: https://www.vlfeat.org/matconvnet/install/#compiling
* Frequently-asked questions to MatConvNet: https://www.vlfeat.org/matconvnet/faq/



