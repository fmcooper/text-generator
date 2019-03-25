# text-generator Readme
This program uses deep learning to generate text from a given sample. 

<a href="https://colab.research.google.com/github/fmcooper/text-generator/blob/master/TextGenerator.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

******************************

1) Program use
2) Google Drive access
3) Results

******************************

## 1) Program use

You will need to have a Google account to access colab. If you have never used colab before take a look <a href="https://colab.research.google.com/notebooks/welcome.ipynb">here</a>. After this, simply click on the following button to open this program in a new colab instance: 
<a href="https://colab.research.google.com/github/fmcooper/text-generator/blob/master/TextGenerator.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

The following variables are available to change: 
* ``NUM_TESTING`` should be a positive integer. If in testing mode then this program will run over the first ``NUM_TESTING`` characters of the sample text
* ``TESTING`` may be set as ``True`` or ``False``. Indicates whether we are in testing mode. 
* ``EMBEDDING_DIMS`` should be a positive integer
* ``RNN_UNITS`` should be a positive integer
* ``NUM_EPOCHS`` should be a positive integer
* ``BATCH_SIZE`` should be a positive integer
* ``BUFFER_SIZE`` should be a positive integer
* Result file locations may also be set. Please see Results section.


## 2) Google Drive access

In order to save the model both during and after training, this program will ask you for google drive access. If you don't want to give access, please comment out the following lines:

```
from google.colab import drive
drive.mount('/content/gdrive')
```

and change this line


```
CHECKPOINT_DIR = F'/content/gdrive/My Drive/Colab/text-generator/checkpoints/' + "epochs" + str(NUM_EPOCHS) + "_batchsize" + str(BATCH_SIZE) + "_embeddingdims" + str(EMBEDDING_DIMS) + "_rnnunits" + str(RNN_UNITS) + "/"     # directory checkpoint weights of model are saved
```

to this:

```
CHECKPOINT_DIR = F'/content/checkpoints/' + "epochs" + str(NUM_EPOCHS) + "_batchsize" + str(BATCH_SIZE) + "_embeddingdims" + str(EMBEDDING_DIMS) + "_rnnunits" + str(RNN_UNITS) + "/"     # directory checkpoint weights of model are saved
```

Now your results files will be saved in the colab virtual machine.

## 3) Results
Checkpoints are saved after each epoch and the entire model is saved after all training. These are reloaded into the program during the testing phase to show how they work. Checkpoints and the entire model are saved to the following directory in your Google Drive: ``Colab/imageClassifier/checkpoints/epochs<NUM_EPOCHS>_batchSize<BATCH_SIZE>_embeddingdims<EMBEDDING_DIMS>_rnnunits<RNN_UNITS>/``. In order to change this, please edit the ``CHECKPOINT_DIR`` constant.
