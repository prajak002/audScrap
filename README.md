


my   Python automation project that automates the downloading hundreds of audio files ) using Selenium, a web-browser automation tool.




# Setup
Install chromedriver via brew or from the [Google site](https://sites.google.com/a/chromium.org/chromedriver/downloads),
and set the location of the chromedriver on your SYSTEM PATH.

I installed the chromedriver via [brew](https://brew.sh/)(command is below), and naturally, brew installs packages to /usr/local/bin, which is already in your $PATH, so that is pretty convenient. You can always do an echo $PATH to make sure that /usr/local/bin is in it, and if it's not in your $PATH variable, then export it by editing either ~/.bash_profile or /etc/paths/.

    $ brew install chromedriver

After installing the chromedriver, here is rest of the setup:

    $ git clone https://github.com/k-chuang/automate-download-freesound.git
    $ cd automate-download-freesound
    $ virtualenv -p /usr/bin/python2.7 venv
    $ source venv/bin/activate
    $ pip install -r dev-requirements.txt
    $ pytest
 
# How to use

Run the command below for more information regarding the arguments (positional or optional, default values, description,   etc.)
 
    $ python automate_download_freesound.py --help
  
There is only one required argument, and that is the desired sounds you wish to download from [Freesound](http://freesound.org). You may list more than one sound, but make sure to separate each one by commas, and if the sound you want to download includes spaces, please put quotation marks around it to ensure a smooth experience.

    $ python automate_download_freesound.py "dogs barking,cats purring"

There are more features and arguments, including download path, file format, sample rate, and advanced filtering. These are all optional arguments, and can help with filtering for your specific needs.

Here is another example, where all the optional arguments are specified:

    $ python automate_download_freesound.py "baby crying,smoke alarm" --download-dir /Users/KevinChuang/Desktop --file-format       wav --sample-rate 48000 --advanced-filter True

This command will download 'baby crying' and 'smoke alarm' wav files with a sampling rate of 48000 from Freesound.org.


# Scripts
[automate_download_freesound.py](https://github.com/k-chuang/automate-download-freesound/blob/master/automate_download_freesound.py) - the main CLI program that uses Selenium to automate downloading sound files from freesound.

[test_automate_download_freesound.py](https://github.com/k-chuang/automate-download-freesound/blob/master/test_automate_download_freesound.py) - the tester program that runs through unit tests and test cases for the main CLI application. 

## License

See the [LICENSE](https://github.com/k-chuang/automate-download-freesound/blob/master/LICENSE) file for license rights and limitations (MIT).

