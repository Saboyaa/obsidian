## Elements
### State
- Shared data structure that holds the current information or context of the application
- Basically the application's memory
### Nodes
- Individual functions or operations that perform specific tasks within the graph
- Each node receives input (often the state), processes it and produces an output (or updates the state)
### Graph
- The structure that the nodes are connected 
- It visually represents the workflow, showing the sequence and conditional paths
### Edges
- The connections between nodes that determine the flow of execution
#### Conditional Edges
- Specialized connections that decide the next node to execute based on specific conditions
### Tools 
- Specialized functions or utilities that nodes can utilize to perform tasks
- A good example is fetching data from an API
#### ToolNode
- A Node whose main job is run a tool
### StateGraph
- Is a class used to build and compile the graph structure
- It manages the nodes, edges, and the overall state, ensuring that the workflow operates in a unified way and that data flows correctly 
### Runnable
- A standardized executable component that performs a specific task
- Allows to create modular systems
### Messages
- Human Message
- System Message
- Function Message
- AI Message
- Tool Message