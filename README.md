# Guardian Aus scraping server installation and setup guide

- Use the latest 20+ Ubuntu image on EC2
- Ensure python 3 is already installed and working (check with python3 -- version). If it is not installed, follow the instructions [here](https://docs.python-guide.org/starting/install3/linux/)

- Install dependencies:

```
sudo apt install firefox python3-pip xvfb x11-utils --yes
```
- find the latest geckodriver release for linux64 here: https://github.com/mozilla/geckodriver/releases
- download, extract and move geckodriver: 

```
wget https://github.com/mozilla/geckodriver/releases/download/v0.30.0/geckodriver-v0.30.0-linux64.tar.gz
tar xzf geckodriver-v0.25.0-linux64.tar.gz
sudo mv geckodriver /usr/bin/geckodriver 
```

- Install selenium etc with pip/pip3


- It may be better to run selenium scripts with xvfb-run or use [pyvirtualdisplay](https://github.com/ponty/pyvirtualdisplay/tree/3.0). This takes care of starting and stopping the Xvfb process which allows headless Firefox to run

- Alternativelt, to manually start Xvfb:

```
Xvfb :10 -ac &
```

- Set the display variable:

```
export DISPLAY=:10
```


Sources:

https://tecadmin.net/setup-selenium-with-firefox-on-ubuntu/

https://gist.github.com/pcgeek86/a1fd9d26f8ad46b51adf9513f67b95f2
