# Theano_VSC

How to set up and use [Theano](https://github.com/Theano/Theano) on the [VSC](https://vscentrum.be/) cluster.

## Installing Theano

Set up your own package repository for Python by following the instructions at: 
[https://vscentrum.be/neutral/documentation/cluster-doc/development/python-packages](https://vscentrum.be/neutral/documentation/cluster-doc/development/python-packages).

Start a GPU cluster by running the following command in the VSC shell:

    qsub -I -l partition=gpu,walltime=0:10:00

Load the following modules to have access to the required libraries (replace `M2070/2014a` by `K20Xm/2014a` depending on which GPU node you are using):

    module load foss/2014a
    module load Python/2.7.6-intel-2014a
    module load foss-cuda/2014a
    module load M2070/2014a

Install Theano by running:

    pip install --install-option="--prefix=${VSC_HOME}/python_lib" theano

## Test Installation

Check correct installing of Theano with GPU support by running check1.py as is [illustrated here](http://deeplearning.net/software/theano/tutorial/using_gpu.html).