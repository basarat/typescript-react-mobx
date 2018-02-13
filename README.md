# typescript-react-mobx
We have a bare bones front end project, with react, types for react, mobx, mobx-react, webpack, webpack-dev-server and offcourse typescript and ts-loader. 


- We have a start script for development 
- We have a build script for when we are ready to deploy our project. 
 
- A basic tsconfig.json that a trivial react setup. 
- A simple webpack.config.js that sets up webpack. 

Our application entry point is `src/app/app.tsx`. There is nothing special up to this point.

Lets imagine we want to create a simple todos application with the requirements: 
* Maintains a list of todos as strings
* Can add a todo
* When you add a todo it is pending
* Can mark todos as done 
* Can mark todos as pending 
* Can remove todos. 

* Any software developer with a basic enginneering degree would easily model this as a class 

```ts
class Todo {
  message: string = '';
  done: boolean = false;
  markAsDone() {
    this.done = true; 
  }
  markAsPending() {
    this.done = false;
  }
}

class ApplicationState {
  todos: Todo[];
  add(message: string){
    const todo = new Todo(); 
    todo.message = message;
    this.todos.push(todo);
  }
  remove(todo: Todo) {
    this.todos = this.todos.filter(t => t!== todo);
  }
}
const state = new ApplicationState();
```
