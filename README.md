## IMPORTANT NOTE

**I have no rights to the code. It is written by X. Fu, S. Jia, L. Zhuang, M. Xu, J. Zhou and Q. Li. I am only using it to figure out how everything works and therefore some parts of the code might deviate from what the original authors wrote.**

This is a realization of the Hyperspectral Anomaly detector proposed in the article: "Hyperspectral Anomaly Detection via DeepPlug-and-Play DenoisingCNN Regularization".

Link to official code: https://github.com/FxyPd/DeCNNAD

## How to run

### Cuda
* Check if your GPU supports CUDA capability by going to: chrome://gpu/
    * If so, download CUDA toolkit at: https://developer.nvidia.com/cuda-toolkit

### Matlab

1. Clone the repository
2. Download Matlab
3. Download ADD-ons: MatConvNet, MinGW, Statistics and Machine Learning Toolbox and Parallel Computing Toolbox
4. Download Visual Studio C++ Compiler

### Running Main_demo.m

1. Change line 426 in "vl_compilenn.m" to have the correct path to your cl.exe file.
    * Example: 
            
            cl_path = 'C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\MSVC\14.29.30133\bin\Hostx64\arm64';
2. Compiling the MatCocNet Add-on
    1. In the Matlab terminal you will have to change the C++ compiler to the Visual Studio compiler. Write the following and choose the Visual Studio C and C++ compiler:

            mex -setup C

            mex -setup C++
    2. Then write one of the following into the terminal (Start with the first. If that doesn't work, try the next command.):
        
            vl_compilenn('enableGpu', true)

            vl_compilenn('verbose', 1, 'enableGpu', true, 'cudaRoot', 'C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8', 'CudaMethod', 'mex') (The path to your cuda toolkit must be specified to your system)

            vl_compilenn('EnableImreadJpeg', false) (Only for testing if the one above does not work)
    3. You can then setup the Add-on by running:
            vl_setupnn
3. You are then ready to run Main_demo.m
    1. In the terminal window, you should go to where matconvnet is stored. Ex.:
            C:\Users\USERNAME\AppData\Roaming\MathWorks\MATLAB Add-Ons\Collections\vlfeat_matconvnet
    2. Then you should run the Main_demo.m by pressing run when opening the fiule in the editor window
    3. You should then get a question wether you would like to add Main_demo.m to matlab path. Press **YES**.
    4. EVrything should then be OK.

### Problems?

More documentation can be found here:

* Installation guide of MatConvNet: https://www.vlfeat.org/matconvnet/install/
* Compilation guide of MatConvNet: https://www.vlfeat.org/matconvnet/install/#compiling
* Frequently-asked questions to MatConvNet: https://www.vlfeat.org/matconvnet/faq/



