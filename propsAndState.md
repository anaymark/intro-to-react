# In your own words, explain the essential differences between props and state in React. Which is immutable or read-only, and which changes? Discuss the answer with your mentor.
* props-defined as the properties, these are the components configuration or options. This is how components talk to each other and interact. They are recieved from above the component and are immutable in the scope of the component. The component **cannot** change it's props but it is responsible for props of child components. Stateless components are ones that usually only utilize the render() function and all their logic is tied in to the props they recieve. 

* state-it is helpful to think of state as something that will change in a componenet, i.e. mutations will occur through user events or interaction and state keeps track of the information in between renders that it does. The keyword here is **user**, state can be thought as the snapshot of the component in that user passed state for the lack of a better word. Components manage their own state, and do not alter state of their children, besides setting the inital state. States can be seen as private to the component. States are optional an increase complexity while reducing predictability. Stateful components are usually used for server communication, processing data, and responding to user events. Anything that can have an external change on the component should be thought of as the state. 


# Built upon your component from the assignment after checkpoint 3, add in state and props to make sure you have fully mastered these core React properties.

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>My First React App</title>
  </head>
  <body>

    <div id="app"></div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/react/16.1.0/umd/react.development.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/16.1.0/umd/react-dom.development.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>>

    <script type="text/babel">

      class Counter extends React.Component {
         constructor(props){
         super(props);
         this.state={
         number: 2018
      }
     }

        render() {
          return (
            <div>
              <h2>Current program: {this.props.label}</h2>
              <h3>Current year: {this.state.number}</h3>
              <p id="timeStamp">Current Time: }</p>
            </div>
          );

        }

      }

    function updateTime(){
    var currentTime = new Date()
    var hours = currentTime.getHours()
    var minutes = currentTime.getMinutes()
    var seconds = currentTime.getSeconds()
    if (minutes < 10){
        minutes = "0" + minutes
    }
    var t_str = hours + ":" + minutes + ":" + seconds + " ";
    if(hours > 11){
        t_str += "PM";
                  } 
    else {
        t_str += "AM";
           }
    document.getElementById('timeStamp').innerHTML = "Current Time: " + t_str;
    }
      setInterval(updateTime, 1);

      const info = {
        date: new Date()
      }

      Counter.defaultProps = {
        label: "Web Developer Track v3"
      }


      ReactDOM.render(
        <Counter
          date={info.date}
          />,document.getElementById('app')
      );
      
    </script>
  </body>
</html>

```


