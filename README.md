# Installing software needed for the course


We'll use IPython notebooks in practical tasks, this instruction is about installing virtual machine with 
needed software. 

After following these instructions, you should see something like this in your browser:

<img src='https://geosci.uchicago.edu/~rtp1/PrinciplesPlanetaryClimate/Python/NotebookQuickstart/Dashboard.png' 
height=400 />


##Linux instructions
Download [folder](https://github.com/iamfullofspam/YSDA_ICL/YSDA.zip) with notebooks and unzip it to your home directory

Install [docker](http://www.docker.com)
Check that it works:

    docker run hello-world
   
Download image of virtual machine (will take a while)

    docker pull mikari/ipython-notebook-rep

Finally run the image

    cd path/to/YSDA
    sudo docker run -d -p 8080:8080 -p 8086:5000 -v $(pwd)/notebooks:/notebooks -v $(pwd)/log:/logdir -v $(pwd)/ipykee:/ipykee mikari/ipython-notebook-rep

open link `localhost:8080` in your browser


## Mac OS instructions

Download [folder](https://github.com/iamfullofspam/YSDA_ICL/YSDA.zip) with notebooks and unzip it to your home directory

Install [docker](http://www.docker.com) (boot2docker to be more precise). Run daemon:

    boot2docker init
    boot2docker start
    $(boot2docker)

Check docker works normally:

    docker run hello-world

Download image of virtual machine (will take a while)
    
    docker pull mikari/ipython-notebook-rep
    
And run the image
    
    cd path/to/YSDA
    docker run -d -p 8080:8080 -p 8086:5000 -v $(pwd)/notebooks:/notebooks -v $(pwd)/log:/logdir -v $(pwd)/ipykee:/ipykee mikari/ipython-notebook-rep

open link `http://192.168.59.103:8080/` in your browser



## Windows instruction:

Download [folder](https://github.com/iamfullofspam/YSDA_ICL/YSDA.zip) with notebooks and unzip it to your home directory

Install [docker](http://www.docker.com) (boot2docker to be more precise). 

Run daemon: click on `Docker>Boot2Docker Start` in your start-up menu

This will open terminal window, all operations further should be executed _in this terminal_. <br/>
Check docker works normally:

    docker run hello-world

Download image of virtual machine (will take a while)
   
    docker pull mikari/ipython-notebook-rep
    
Automagically, your Windows `C:/Users/` directory is mounted as `/c/users/`, so let's move 
to mounted YSDA folder 
        
    cd /c/Users/path/to/YSDA
    sudo docker run -d -p 8080:8080 -p 8086:5000 -v $(pwd)/notebooks:/notebooks -v $(pwd)/log:/logdir -v $(pwd)/ipykee:/ipykee mikari/ipython-notebook-rep

open link `http://192.168.59.103:8080/` in your browser.
