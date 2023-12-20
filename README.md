## 🚀 Getting Started

Follow these steps to set up and run on your local machine.

### 📋 Prerequisites

- Python >=3.8.0
- An OpenAI API key
- Windows OS (Not tested on others)
- FFmpeg 




<details>
<summary>Windows</summary>
If FFmpeg is not installed in your system, you can follow the steps below to install it.

First, you need to install Chocolatey, a package manager for Windows. Open your PowerShell as Administrator and run the following command:
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
Once Chocolatey is installed, you can install FFmpeg by running the following command in your PowerShell:
```
choco install ffmpeg-full
```
Please ensure that you run these commands in a PowerShell window with administrator privileges. If you face any issues during the installation, you can visit the official Chocolatey and FFmpeg websites for troubleshooting.
</details>

<details>
<summary>macOS</summary>
If FFmpeg is not installed in your system, you can follow the steps below to install it.

    brew install ffmpeg
    brew install portaudio
    brew install python-tk
    
    You might need to change the index of your speaker depending on your setting to 0 or 1
    on line 55 AudioRecorder.py

</details>

### 🔧 Installation

1. Clone the repository:

2. Navigate to the folder:


3. Install the required packages:

   ```
   pip install -r requirements.txt
   ```
   
4. Create a `keys.py` file in the ecoute directory and add your OpenAI API key:

   - Option 1: You can utilize a command on your command prompt. Run the following command, ensuring to replace "API KEY" with your actual OpenAI API key:

      ```
      python -c "with open('keys.py', 'w', encoding='utf-8') as f: f.write('OPENAI_API_KEY=\"API KEY\"')"
      ```

   - Option 2: You can create the keys.py file manually. Open up your text editor of choice and enter the following content:
   
      ```
      OPENAI_API_KEY="API KEY"
      ```
      Replace "API KEY" with your actual OpenAI API key. Save this file as keys.py within the ecoute directory.


### 🎬 Running

Run the main script:

```
python main.py
```

For a better and faster version, use:

```
python main.py --api
```

Upon initiation, it will begin transcribing your microphone input and speaker output in real-time, generating a suggested response based on the conversation. Please note that it might take a few seconds for the system to warm up before the transcription becomes real-time.

The --api flag significantly enhances transcription speed and accuracy, and it's expected to be the default option in future releases. However, keep in mind that using the Whisper API will consume more OpenAI credits than using the local model. This increased cost is attributed to the advanced features and capabilities that the Whisper API provides. Despite the additional cost, the considerable improvements in speed and transcription accuracy might make it a worthwhile investment for your use case.
