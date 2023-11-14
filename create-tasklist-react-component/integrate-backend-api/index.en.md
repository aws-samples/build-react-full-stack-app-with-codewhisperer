## Integrate with Backend API

1. Navigate to TaskList.js file and locate handle submit function, with in function append below comment to integate Add button click with backend service

```
// use fetch to post new task to server
```

2. Keep generating suggestion untill your find generated suggestion as below
```
// use fetch to post new task to server
        fetch('/tasks', {
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
```


3. To Get tasks from server on render on Component loaded event,  add below comment to generate suggestion

```
//  GetTasks function to get tasks list from server and set state
```

Sample Code:
```
//  GetTasks function to get tasks list from server and set state
    GetTasks() {
        fetch('/tasks')
            .then(res => res.json())
            .then(tasks => this.setState({ tasks }));
    }
    // create a function to get tasks list from server and set state
    
    componentDidMount() {
        this.GetTasks();
    }

```

4. Now you TaskList.js component should look as below

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

5. Navigate to preview where you will get your application must be showing error as shown below because we haven't create backend service yet
![Preview](/static/preview4.png)


Its time to create NodeJS server, Keep Going

### 📁 Next: [Create Node Service](/create-nodejs-service/index.en.md)