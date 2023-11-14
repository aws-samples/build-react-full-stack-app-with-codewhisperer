## Add Tasks State to React Component

### Add constructor 

1. Navigate to TaskList.js file and in order to add constructor add below prompt to generate suggestions

```
// create constructor to initialize tasks state and new task state
```

2. Keep generating suggestion untill your react component has code as below
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
    
    render() {
        return (
            <div>
                <ul>
                    <li>Task 1</li>
                    <li>Task 2</li>
                    <li>Task 3</li>
                </ul>
            </div>
        );
    }
}

// export the component

export default TaskList;

```

3. Delete generated Render function and add below comment to generate suggestion

```
// render the list of tasks and  input field to add new task, add a add task button to add  new task
```

4. Dont Forget to add closing braces } of render function. Now you TaskList.js component should look as below

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

5. Navigate to preview where you will get your application rendered as below
![Preview](/static/preview2.png)

6. To Test you application, add dummy task and click on Add button
![Preview](/static/preview3.png)


Congratulations! you are able to create a functional react application without leaving your IDE and browsing through different tech forums.

Good Job! keep going one more step to complete in this section

### 📁 Next: [Integrate Backend API](/create-tasklist-react-component/integrate-backend-api/index.en.md)
