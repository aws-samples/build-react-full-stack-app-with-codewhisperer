## Create Development environment

MERN Stack (MongoDB, ExpressJS, ReactJS, and NodeJS) is the one of most popular stack in this competitive age, you will try to complete a few challenges. CodeWhisperer is designed to improve your productivity. You are not going to experience that productivity gain following step-by-step instructions. Don’t worry, we have provided a few hints to help you along way if you get stuck.

![MERN Stack](/static/MernStack.png)

For this challenge, assume you are react application developer and you have to create complete development environment from the scratch which includes creating react application & node js server. Please familiarize yourself with VSCode environment.

![File Explorer](/static/vscode1.png)

In this challenge you must complete one task:
1. In the directory MERNStack, open the file environment.sh. Please copy below prompts in to guide you to create Dev environment:

``` 
# make folder for dev

# create react app named tasks-app



############################################################################


# go to tasks-app folder


# create new folder for node environment for backend


# create a new npm package for backend project



# install express


# install cors


# install mongoose

##########################################################################

# go to tasks-app folder

# run tasks-app


``` 

2. Navigate to end of each comment and press Enter to generate code



3. In VS Code navigate to File Menu, go to Terminal, create new Terminal and run .\environment.sh

```
.\environment.sh
```

![Create Environment](/static/terminalpreview1.png)

4. If you are using your local IDE, you will find environment is being created, please wait while dependencies are being installed, In the few minutes you will see react application launched
![React App](/static/reactapp1.png)

5. If you are using VSCode-Web then you have to open click on Open on Browser Button and replace /proxy/ with : in url
![Create Environment](/static/terminalpreview2.png)

![React App](/static/reactapp2.png)


No! Don't give up! OK, if you are stuck, here is the complete solution for environment.sh:

``` 
# make folder for dev
mkdir dev
cd dev

# create react app named tasks-app
npx create-react-app tasks-app


############################################################################


# go to tasks-app folder
cd tasks-app


# create new folder for node environment for backend
mkdir backend
cd backend


# create a new npm package for backend project
npm init -y

# install express
npm install express --save

# install cors
npm install cors --save

# install mongoose
npm install mongoose --save

##########################################################################

# go to tasks-app folder
cd ../

# run tasks-app
npm start




```

6. [MongoDB community edition](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/) is already installed on instance, Please validate by opening new Terminal
and try mongosh command
![MongoShell](/static/mongoshell.png)

Great work! Let’s move on to the next challenge.

### 📁 Next: [Create Tasklist React Component](/create-tasklist-react-component/index.en.md)