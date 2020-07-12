
# Bangkit-JKT1A
This directory host the [demonstration site](https://odir.simulasikan.com/) of Ocular Disease Intelligent Recognition (ODIR) Classification using Tensorflow as a Final Project of [Google Bangkit Machine Learning Academy](https://events.withgoogle.com/bangkit/) by team JKT1-A

Team:

 - Azhari Haris Al Hamdi
 - Bimantara Hanumpraja
 - Irfani Sakinah
 - R. Achmad Dadang Nur Hidayanto


# Demo
 - Web based: [ODIR-Classification Site](https://odir.simulasikan.com/)

# Slide
[Presentation](https://docs.google.com/presentation/d/1lZIzMBJ5Iy4O6xXg61bEtknCgW64KHmjypyg8GA2WYU/edit?usp=sharing)

# Repository 
Complete project files including model files (h5 format, tflite, and js files) are available to download at [Our cloud storage](https://cloud.dadangnh.com/s/jk3Ew8YaSf9jazW).

# Deployment
To deploy the site, do the following:

First, clone this repository:

```bash
$ git clone git@github.com:bangkitjkt/final-project-ODIR5K.git
```

Run the model to train new data from model directory

```bash
$ ipython
$ %run choose_one_model.ipynb
```

Extract the model into Tensorflow.js files:

```bash
$ ipython
>> pip install tensorflowjs
>> import tensorflowjs as tfjs
>> tfjs.converters.save_keras_model(model, 'path_to_tfjs/')
```

You will get output like:

```bash
$ ls -la path_to_tfjs/
total 30420
-rw------- 1 root root 4194304 Jun 20 13:15 group1-shard1of8.bin
-rw------- 1 root root 4194304 Jun 20 13:15 group1-shard2of8.bin
-rw------- 1 root root 4194304 Jun 20 13:15 group1-shard3of8.bin
-rw------- 1 root root 4194304 Jun 20 13:15 group1-shard4of8.bin
-rw------- 1 root root 4194304 Jun 20 13:15 group1-shard5of8.bin
-rw------- 1 root root 4194304 Jun 20 13:15 group1-shard6of8.bin
-rw------- 1 root root 4194304 Jun 20 13:15 group1-shard7of8.bin
-rw------- 1 root root 1767712 Jun 20 13:15 group1-shard8of8.bin
-rw------- 1 root root   21782 Jun 20 13:15 model.json
```

Then, upload the model to the web server

```bash
$ scp -r path_to_tfjs/ remote_username@server_ip:/path_to_model_site
```

Change model url on `index.js` file (line 36921)

Last, upload the web to your server
```bash
$ scp -r web/ remote_username@server_ip:/path_to_web
```
