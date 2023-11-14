## Configure Node endpoint

1. Now navigate In File Explorer MERN_Stack\Dev\tasks-app\src\components folder and open  Tasks.js file

2. Search for fetch in handleSubmit & GetTasks and update endpoint to http://localhost:5000/tasks or http://ec2-XXXXXXXXX.compute-1.amazonaws.com:5000/tasks (replace XXXXXXXXX in url with your ec2 public endpoint) at both places. 
```
    // create a function to handle the submit of the input field
    handleSubmit(event) {
        event.preventDefault();
        this.setState({
            tasks: [...this.state.tasks, this.state.newTask],
            newTask: ''
        });
        // use fetch to post new task to server
        fetch('http://localhost:5000/tasks', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                task: this.state.newTask
            }
            )
        }
        );
        
    }

//  GetTasks function to get tasks list from server and set state
    GetTasks() {
        fetch('http://localhost:5000/tasks')
            .then(res => res.json())
            .then(tasks => this.setState({ tasks }));
    }
```

3. Update setState function in GetTasks to assign array of tasks
```
//  GetTasks function to get tasks list from server and set state
    GetTasks() {
        fetch('http://localhost:5000/tasks')
            .then(res => res.json())
            .then(tasks => this.setState({ tasks : tasks.map(p=>p.task)}));
    }
```
 


3. Navigate to Preview of your Node application at http://localhost:3000/.

![Preview](/static/preview5.png)

Try adding sample tasks, hit refresh and Congratulations! now you have all tasks are persisted in database
![Preview](/static/preview6.png)

No! if you are stuck, here is the complete TaskList.js file

```
// import react

import React from 'react';

// create a react component class to display a list of tasks 

class TaskList extends React.Component {

//create constructor to initialize tasks state and new task state
    constructor(props) {
        super(props);
        this.state = {
            tasks: [],
            newTask: ''
        };
        this.handleChange = this.handleChange.bind(this);
        this.handleSubmit = this.handleSubmit.bind(this);
    }
    // create a function to handle the change of the input field
    handleChange(event) {
        this.setState({
            newTask: event.target.value
        });
    }
    // create a function to handle the submit of the input field
    handleSubmit(event) {
        event.preventDefault();
        this.setState({
            tasks: [...this.state.tasks, this.state.newTask],
            newTask: ''
        });
        // use fetch to post new task to server
        fetch('http://localhost:5000/tasks', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                task: this.state.newTask
            }
            )
        }
        );
        
    }

//  GetTasks function to get tasks list from server and set state
    GetTasks() {
        fetch('http://localhost:5000/tasks')
            .then(res => res.json())
            .then(tasks => this.setState({ tasks: tasks.map(p=>p.task) }));
    }
    // create a function to get tasks list from server and set state
    
    componentDidMount() {
        this.GetTasks();
    }



// render the list of tasks and  input field to add new task, add a add task button to add  new task
    render() {
        return (
            <div>
                <ul>
                    {this.state.tasks.map(task => <li>{task}</li>)}
                </ul>
                <form onSubmit={this.handleSubmit}>
                    <input type="text" value={this.state.newTask} onChange={this.handleChange} />
                    <button>Add Task</button>
                </form>
            </div>
        );
        }


    
}

// export the component

export default TaskList;

```


### 📁 Next: [Run Security Scan](/run-security-scan/index.en.md)