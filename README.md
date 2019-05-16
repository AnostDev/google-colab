# Google Colab ?


Google colab is an execucutable document that allows you to write run and share code within Google Drive.

**Briefly, Colab can be seen as a sharable Jupyter Notebook.**

## Setting up colab for a remote machine (AWS)

> Step 1:
- Launch your EC2 machine and link it to a security group which allows ssh on port 22\
- Install python/3 pip/3 and jupyter\
`ssh -i path-key user@public-dns -L 8888:localhost:8888` (aws)\
Don't forget to forward the port (here 8888)\
`python3 -m install pip --upgrade pip`\
If there is an error with pip (cannot find), add `alias pip=pip3` to ~/.bashrc\
`pip install jupyter`

>Step 2: Install and enable the jupyter_http_over_ws jupyter extension (one-time)
The jupyter_http_over_ws extension is authored by the Colaboratory team and available on GitHub.**

- `pip install jupyter_http_over_ws`
- `jupyter serverextension enable --py jupyter_http_over_ws`

> Step 3: Start server and authenticate
New notebook servers are started normally, though you will need to set a flag to explicitly trust WebSocket connections from the Colaboratory frontend.

```c
jupyter notebook \
  --NotebookApp.allow_origin='https://colab.research.google.com' \
  --port=8888 \
  --NotebookApp.port_retries=0 --no-browser
```
**You want to install some packages directely from your notebook ?**\
Simply enter `!pip install package-name` and do not forget the `!`, because pip is a command line tool not a command line

## Why use colab ?

Colab contains **built-in libraries**, and allows you to insert snippets code in your document.

**Share** with your team for live work.

Your Notebook can be **exported to github**.

You can find and explore many **notebooks online** and just click to export theù to your colab environment.\
_Ex: the seedbank repository research.google.com/seedbank_

You want to know more, check it out on colab.research.google.com


## Demo: Tensorflow on Colab
Code train and test a NN.
