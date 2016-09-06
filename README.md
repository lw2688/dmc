# DMC 2016 Virtual Machine

This Vagrant setup automates the installation of a full machine learning software stack running on Ubuntu 14.04.

What's in the box:
* [Keras](http://keras.io/) - minimalist, highly modular neural networks library.
* [Theano](http://deeplearning.net/software/theano/) - library to define, optimize, and evaluate mathematical expressions involving multi-dimensional arrays efficiently.
* [Tensorflow](https://www.tensorflow.org/versions/r0.7/api_docs/index.html) - library for numerical computation using data flow graphs.
* [Jupyter](http://jupyter.readthedocs.org/en/latest/index.html) - web application to create, share documents that contain live code, equations, visualizations and explanatory text.

![Keras](http://imgur.com/nE0of8d.jpg "Keras")
![Theano](http://i.imgur.com/Bb5SHxW.png "Theano")
![TensorFlow](http://imgur.com/rwISEz5.jpg "TensorFlow")
![Jupyter](http://i.imgur.com/zpzIAml.jpg "Jupyter")

# Requirements

You must install VirtubalBox and Vagrant before continuing:

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

At the top of the page under "VirtualBox platform packages" download the installation file according to your operating system (Windows or OSX) and go through the installation process.

* [Vagrant](https://www.vagrantup.com/downloads.html)

Select your operating system to download the installation file, then go through the installation process.

# Getting started

Once Vagrant and VirtualBox are installed, clone this repository or import `Vagrantfile` and `bootstrap.sh` in a directory.

From this directory, let's start your Vagrant box by typing in your terminal (it might take some time to download the Ubuntu image):

    $ vagrant up
Once the setup is complete, just run:

    $ vagrant ssh
You are in! Now, let's train your first recurrent neuronal network:

    $ python keras/examples/addition_rnn.py

If you can see that, it means that you setup is working and that you are training your recurrent neuronnal network to perform addition!
![addition_rnn-screenshot](http://i.imgur.com/u06tE6B.png)

To go through the code step by step, type:

    $ jupyter notebook --no-browser --ip=0.0.0.0 --FileContentsManager.root_dir=/home/vagrant/keras/examples/

Open a browser and browse http://127.0.0.1:8888

# Tips and tricks

To access files present on your computer from your Vagrant/Ubuntu machine, go to the `/vagrant` directory which is mounted to the directory you started you Vagrant box from:

    $ cd /vagrant/

To get a list of available vagrant commands (from your host computer), just type:

    $ vagrant

If you want to start your virtual machine from scratch, disconnect from it and from your host computer run:

    $ vagrant destroy
    $ vagrant up
