# AI Voice Cloning

> **Note** I do not plan on actively working on improvements/enhancements for this project, this is mainly meant to keep the repo in a working state in the case the original git.ecker goes down or necessary package changes need to be made.

That being said, some enhancements added compared to the original repo:

:heavy_check_mark: Possible to train in other languages

:heavy_check_mark: Hifigan added, allowing for faster inference at the cost of quality.  

:heavy_check_mark: whisper-v3 added as a chooseable option for whisperx

:heavy_check_mark: Output conversion using RVC 

This is a fork of the repo originally located here: https://git.ecker.tech/mrq/ai-voice-cloning.  All of the work that was put into it to incoporate training with DLAS and inference with Tortoise belong to mrq, the author of the original ai-voice-cloning repo.  

## Setup
Check my youtube video for instruction https://youtu.be/wuB8GLdS7-4?si=z_Y5KxGpPcLycnB6 <br>
This instruction For setup on [Runpod.io](https://runpod.io?ref=c0v5p0ys) , if you don't have runpod account create one and add credit minimum 10USD

#### Alternative Manual Installation

In runpod choose template <br>
<img width="446" alt="Screenshot 2025-02-14 at 19 29 08" src="https://github.com/user-attachments/assets/43fe3dcc-72bb-42f8-a423-6edbdf3e6281" /> <br>
Pod setup lool like this <br>
<img width="828" alt="Screenshot 2025-02-14 at 19 40 12" src="https://github.com/user-attachments/assets/605f898b-5d5a-4619-b6fb-5dd3865d7f06" /> <br>

1. Clone the repository
```
git clone https://github.com/gordon123/ai-voice-cloning.git
```
** this repo I updated only main.py to run on the gradio public all the work go to https://github.com/JarodMica/ai-voice-cloning or his Youtube tutorials below

2. create venv type
    ```
    python -m venv venv
    ```
    activate it
   ```
    source /workspace/venv/bin/activate
    ```
   now you should see (venv) at the begining of the command line
4. run
    ```
    cd ai-voice-cloning
    
    bash setup-cuda.sh
    ```
    It will start running through all of the python packages needed !!! WAIT WAIT WAIT <br>
    For sometime it will show this error , hit Ctrl+ C to exist <br>
    ```
    import tkinter as tk
    ModuleNotFoundError: No module named 'tkinter'
    ```
    Ctrl + C to exist then type

    ```
    apt-get update
    apt-get install python3.11-tk
    ```

6. After it finishes, run
   ```
   bash start.sh
   ```
   For this first time and this will start downloading most of the models you'll need. WAIT WAIT WAIT!!!!! <br>
    - Some models are downloaded when you first use them.  You'll incur additional downloads during generation and when training (for whisper).  However, once they are finished, you won't ever have to download them again as long as you don't delete them.  They are located in the ```models``` folder of the root.


    If you see this message ```Removing weight norm...Loaded vocoder model....Loaded TTS, ready for generation.``` then look up find Gradio link like in this photo <br>
    <img width="1060" alt="Screenshot 2025-02-14 at 19 51 50" src="https://github.com/user-attachments/assets/08029d17-4904-4cc8-ae45-7c013f1ccd69" /> <br>
    you should see something like this ```Running on public URL: https://7f6e62958285392788.gradio.live``` copy this link to browser and test to generate some text
    Have fun!! <br>
    <br>
   Lastly, delete your pod after you download your training model or any generated files, otherwise Runpod will charge you over time! <br>
<img width="412" alt="Screenshot 2025-02-14 at 20 36 23" src="https://github.com/user-attachments/assets/8b889afe-77ca-40ce-9c04-475d1ff2f976" /> <br>
### CLICK THE BIN ICON, IT WILL PERMANENTLY DELETE EVERYTHING, BACK UP FILES YOU NEED FIRST ###

8. **(Optional)** You can opt to install whisperx for training by running ```setup-whipserx.bat```
    - Check out the whisperx github page for more details, but it's much faster for longer audio files.  If you're processing one-by-one with an already split dataset, it doesn't improve speeds that much.

## Instructions
Checkout the YouTube video:

Watch First: https://youtu.be/WWhNqJEmF9M?si=RhUZhYersAvSZ4wf

Watch Second (RVC update): https://www.youtube.com/watch?v=7tpWH8_S8es&t=504s

Everything is pretty much the same as before if you've used this repository in the past, however, there is a new option to convert text output using ```rvc```.  Before you can use it, you will need a **trained** RVC .pth file that you get from RVC or online, and then you will need to place it in ```models/rvc_models/```.  Both .index and .pth files can be placed in here and they'll show up correctly in their respective dropdown menus.

To enable rvc: 
1. Check and enable ```Show Experimental Settings``` to reveal more options
2. Check and enable ```Run the outputter audio through RVC```.
You will now have access to parameters you could adjust in RVC for the RVC voice model you're using.

