## Create TaskList React Component

### Add Task List React component
Now you have your first React app running, Find out how to build end to end solution quickly and intuitively.

1. In File Explorer MERN_Stack\Dev\tasks-app folder Navigate to src folder

2. Create components folder in src

3. Create a new file TaskList.js in components folder

(Optional)-you can also open a new terminal create TaskList component using below script:
``` 
cd dev/tasks-app/src
mkdir components
cd components
touch TaskList.js
```

4. Open TaskList.js file, add below prompt and press enter to generate suggestions
```
// import react
```

5. Add below prompt and press enter to generate suggestions
```
// create a react component class to display a list of tasks 
```

6. your generated TaskList component code should be similar as below

```
// import react

import React from 'react';

// create a react component class to display a list of tasks 

class TaskList extends React.Component {

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

7. Now in order to integrate your TaskList component in React App, navigate to src\App.js file and open

8. Add below comments at line#3 to generate suggestion to import TaskList component
```
// import TaskList
```

9. Delete compelete function App()

10. Add below prompt to generate suggestions
```
// app function to display TaskList
```

11. Navigate to Preview of your React application, now it must be displaying your list of Tasks

![Preview](/static/preview1.png)

No! if you are stuck, here is the complete App.js file

```
import logo from './logo.svg';
import './App.css';
// import TaskList
import TaskList from './components/TaskList';

// app function to display TaskList
function App() {
  return (
    <div className="App">
      <TaskList />
    </div>
  );
} 

export default App;

```


### 📁 Next: [Modify Tasklist](/create-tasklist-react-component/modify-tasklist-and-add-state/index.en.md)