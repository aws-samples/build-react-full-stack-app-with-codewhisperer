## Create Node Service

### Introducing Node
Node (or more formally Node.js) is an open-source, cross-platform runtime environment that allows developers to create all kinds of server-side tools and applications in JavaScript.

### Introducing Express
Express is the most popular Node web framework, and is the underlying library for a number of other popular Node web frameworks. It provides mechanisms to write handlers for requests with different HTTP verbs at different URL paths

Now you have your React app running, Find out how to build Node Service quickly and intuitively.

1. In File Explorer MERN_Stack\Dev\tasks-app folder Navigate to backend folder

2. Create index.js file

(Optional)-you can also open a new terminal create index.js component using below code:
```
cd dev/tasks-app/backend
touch index.js
```

4. Open index.js file, add below prompt and press enter to generate suggestions

```
// node express server for tasks api integrated with mongoDB
```


6. Press right arrow key to generate suitable suggessions as shown below

```
// node express server for tasks api integrated with mongoDB with Task Model

const express = require('express');
const app = express();
const cors = require('cors');
const mongoose = require('mongoose');
const Task = require('./models/Task');
const PORT = process.env.PORT || 5000;

app.use(cors());
app.use(express.json());

mongoose.connect('mongodb://localhost:27017/tasks', { useNewUrlParser: true, useUnifiedTopology: true }
    , () => {
        console.log('Connected to DB');
    }
    );

// get tasks endpoint    
app.get('/tasks', async (req, res) => {
    const tasks = await Task.find();
    res.json(tasks);
}
    );

// post tasks endpoint  
app.post('/tasks', async (req, res) => {
    const task = new Task(req.body);
    await task.save();
    res.json(task);
}
    );
    
app.put('/tasks/:id', async (req, res) => {
    const task = await Task.findByIdAndUpdate(req.params.id, req.body);
    res.json(task);
}
    );

// delete tasks endpoint   
app.delete('/tasks/:id', async (req, res) => {
    const task = await Task.findByIdAndDelete(req.params.id);
    res.json(task);
}
    );

// listen to port    
app.listen(PORT, () => {
    console.log('Server started on port ' + PORT);
}
    );
    


```

7. In case mongoose.connect has callback in generated code, Please remove below code from mongoose.connect as mongoose latest library longer support callbacks
```
, () => {
        console.log('Connected to DB');
    }

```

8. Create a new folder models in backend folder

9. Create a new file Task.js in models folder

10. Open Task.js and add below comments
```
// Task model
```

11. Press right arrow key to generate suitable suggessions as shown below

```
// Task model

const mongoose = require('mongoose');

const taskSchema = new mongoose.Schema({
    title: {
        type: String,
        required: true
    }
});
const Task = mongoose.model('Task', taskSchema);

module.exports = Task;
```

12. Change Property name from title to task
```
// Task model

const mongoose = require('mongoose');

const taskSchema = new mongoose.Schema({
    task: {
        type: String,
        required: true
    }
});

const Task = mongoose.model('Task', taskSchema);

module.exports = Task;
```

9. Open index.js and add below comment to generate suggestion for get endpoint at root
```
// get app endpoint
```

Sample code
```
// get app endpoint

app.get('/', (req, res) => {
    res.send('Hello World!');
}
    );
```
10. Open new Terminal from file explorer and run below script to run Node server
```
cd ./dev/tasks-app/backend
node index.js
```

11. Navigate to Preview of your Node application at http://localhost:5000/.

![Preview](/static/nodepreview.png)
Or open Navigate to http://XXXXXXXXXXXXX.compute-1.amazonaws.com/proxy/5000/
![Preview](/static/nodehelloworld1.png)

Try fetching http://localhost:5000/tasks and you will see empty json array of tasks
![Preview](/static/nodepreview1.png)

No! if you are stuck, here is the complete index.js file

```
// node express server for tasks api integrated with mongoDB

const express = require('express');
const app = express();
const cors = require('cors');
const mongoose = require('mongoose');
const Task = require('./models/Task');
const PORT = process.env.PORT || 5000;

app.use(cors());
app.use(express.json());

mongoose.connect('mongodb://localhost:27017/tasks', { useNewUrlParser: true, useUnifiedTopology: true }
    
    );

// get app endpoint

app.get('/', (req, res) => {
    res.send('Hello World!');
}
    );
    
app.get('/tasks', async (req, res) => {
    const tasks = await Task.find();
    res.json(tasks);
}
    );
    
app.post('/tasks', async (req, res) => {
    const task = new Task(req.body);
    await task.save();
    res.json(task);
}
    );
    
app.put('/tasks/:id', async (req, res) => {
    const task = await Task.findByIdAndUpdate(req.params.id, req.body);
    res.json(task);
}
    );
    
app.delete('/tasks/:id', async (req, res) => {
    const task = await Task.findByIdAndDelete(req.params.id);
    res.json(task);
}
    );
    
app.listen(PORT, () => {
    console.log('Server started on port ' + PORT);
}
    );
    

```


### 📁 Next: [Configure Nodejs endpoints](/create-nodejs-service/configure/index.en.md)