#   Components

-   Components describes the face of UI.
-   They are `reusable` & can be nested inside other.

-    There are two Types of Components.
    -   Stateless Functional Components.
    -   Statefull Class Components.

1.  **Stateless Functional Components**
    -   Javascript Function.
    -   ```js
        function Welcome(props) {
            return <h1> Hello, {props.name} </h1>
        }
        ```

2.  **Statefull Class Components**
    -   Class rendering Component class : *rendering method return HTML*.
    -   ```js
        class Welcome extend React.Component {
            render() {
                return <h1> Hello, {this.props.name} </h1>
            }
        }
        ```