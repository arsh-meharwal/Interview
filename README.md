# Interview
Interview Prep Readme
# Interview Prep

- **OOPS concept in programming**
    - **What is OOPS ?**
        
        Ek Programming ka usool/ model/ pattern hai ye, data aur functions ko logically group karte hai jis se ki code reusable ban jata hai.  Iske 4 key concepts hai. Shortcut - ( API ) E
        
        - Abstraction / `संक्षेप` / brief
            
            Hiding unnecessary details and showing only the relevant part of the code. E.g - fetch().
            
        - Polymorphism / Poly `अनेक` Morph `रूप`
            
            Ek hi function me different arguments pass krke ham us function ke anek roop me istemal kar sakte hai.
            
        - Inheritance / `विरासत`
            
            JS ke har ek Object & Array (except those explicitly created with Object.create(null)) “Prototype” naam ke object ko inherit karta hai. Ye ek inheritance ka example hai, some examples of prototype objects are
            
            - .hasOwnProperty(””) - checks any key (if exists) in an Object
            - .pop() - Inherited by an Array
        - Encapsulation
            - Data(Variables) + Method(Functions) ko single unit me combine karna
            - Purpose for this is to keep the data safe from external interference and modify it through only allowed methods for data integrity.
            - Function scope and data + methods encapsulation ka example.
            
            ```jsx
            function Person(name, age) {
              let _name = name; //  variable, data
              let _age = age;   //  variable, data
            
              // Public method to access the private data
              return {
                getName: function() {
                  return _name;
                },
                getAge: function() {
                  return _age;
                },
                setAge: function(newAge) {
                  if (newAge > 0) {
                    _age = newAge;
                  }
                }
              };
            }
            ```
            
    - Why is this used ?
        - Code Re-usability
        - Code Readability
        - Maintainablilty
        - Data Integrity
    - Where ?
        
        We must follow OOPS guidelines for a better coding environment.
        
    - When ?
        
        Every Code project that we do we should use it.
        
- **HTML**
    
    **Markup** ek tags ka set hota hai jis se ham text ko arrange & structure kar sakte hai. Markup languages kai prakar ki hoti hai jaise ki 
    
    1. HTML (Hyper Text Markup Language)
        - Web pages banane ke liye use hoti hai.
        - Structure aur content ko define karne ke liye use hoti hai, jaise headings, paragraphs, links, images, etc.
    2. XML (eXtensible Markup Language)
        - XML ka use data ko describe karne ke liye hota hai.
        - Yeh ek flexible markup language hai jisme custom tags banaye ja sakte hain.
    3. Markdown 
        - Markdown ek lightweight markup language hai jo text ko simple syntax ke saath format karne ke liye use hoti hai.
        - Commonly use hoti hai **README** files, documentation, aur writing content for the web.
- Node JS
    - API
    - Routing
    - MVC Architecture
    - Express
    - res & req Objects
    - Types of Http requests
    - Authorization & Authentication
    - JWT
        
        JWT ek token hota hai jisko server bhejta hai user ke paas uske credentials verify karne ke baad. Isme ek lamba sa string hota hai jo ki . se separated hota hai.
        
        Iske fayde
        
        - Server ko sessions nhi banane padte
        - Lightweight aur easily exchangable
        
        Nukasaan
        
        - Ek baar token bhejne ke baad revoke nhi kar sakte uske particular time tak
    - Redis for DB Caching
    - Long Polling
    - Web Sockets? When, Where, How?
    - JWT
- MongoDB
    - Schema
    - DB Modelling
- JavaScript
    - `Class` & `Constructor` in JS
        
        JS class ek object banane ka tarika hota hai jiske andar kuch key-value pairs ko aur kuch functions ho un key-value pairs ko manipulate karne ke liye. Is object structure ko hamko `class` se define karna hota hai aur `new` se banana hota hai
        
        E.g of a `class` in JavaScript
        
        ```jsx
        // node of a linked list
        class node {
        	constructor(value){
        		this.value=value
        		this.next=null  //it will be set when list is made
        	}
        }
        ```
        
        **`Constructor`** - Jab bhi ham kisi class ka object banate hai (via **new** keyword), constructor method us class ke liye automatic call hota hai. Iska kaam initial values ya setup karna hai jo object ko banate waqt chahiye hote hain. 
        
        > **Kya `constructor` ke bina `class` bana sakte hai ? = Haa bana sakte hai**
        > 
        
        ```jsx
        class Animal {}
        const dog = new Animal(); // Default constructor ka use ho raha hai
        console.log(dog); // Output: Animal {}
        ```
        
        - Simple Class Function
            
            ```jsx
            class Person {
              constructor(name, age) {
                this.name = name; // Instance property
                this.age = age;
              }
            
              getDetails() {
                return `${this.name} is ${this.age} years old.`;
              }
            }
            
            const person1 = new Person("John", 25);
            console.log(person1.getDetails()); // Output: "John is 25 years old."
            ```
            
        - A `Class` extending another `Class` (Inheritance)
            
            ```jsx
            class Animal {
              constructor(type) {
                this.type = type;
              }
            }
            
            class Dog extends Animal {
              constructor(name) {
                super("Dog"); // Parent class ka constructor call kar rahe hain
                this.name = name;
              }
            
              getInfo() {
                return `${this.name} is a ${this.type}`;
              }
            }
            
            const dog = new Dog("Buddy");
            console.log(dog.getInfo()); // Output: "Buddy is a Dog"
            ```
            
    - Scope? Hoisting & T.D.Z ?
    - Closures ? Lexical Scope ? Scope Chaining ?
    - Cookies, Local Storage, Session Storage?
    - Web APIs ?
    - How are async tasks executed in JS?
    - Event Loop ?
    - How Code is executed in JS ?
    - What is Promises ?
- React
    - React Component ? Types of React Components
        
        A reusable piece of code that uses JSX code return an UI. may contain JS functions & React Hooks that manipulate the UI.
        
        - Class Component
        - Functional Component
        - Pure Component
            
            Pure Component wo hota hai jo ki props ya state ka shallow comparison karta hai re-rendering ke liye. Agar props/state ki first level value me koi change nhi hota to ye re-render nhi karega pure component ko. Nested values of Props/state ko ye comapre nhi karta bas first level values ko karega. We can create a pure component by using React.memo()
            
            ```jsx
            import React from "react";
            
            const MyComponent = React.memo(({ name }) => {
              console.log("Rendered");
              return <div>{name}</div>;
            });
            
            export default MyComponent;
            ```
            
        - High Order Component
            
            HOC ek **pure function(dosen’t modify the original func^)** hai jo ki existing React Component ki functionality enhance karta hai. HOC takes one component as input and returns another component
            
            ```jsx
            const User = () => {
              return <h1>Hello User</h1>;
            };
            
            //withLoginCheck is HOC
            const withLoginCheck = (WrappedComponent) => {
            // returning a function here
              return (props) => {
                const isLoggedIn = props.isLoggedIn; // Login ka status check karte hain
                if (!isLoggedIn) {
                  return <h1>Please Login</h1>; // Agar login nahi, to ye dikhayenge
                }
                return <WrappedComponent {...props} />; // Agar login hai, to original component dikhayenge
              };
            };
            
            const UserWithLoginCheck = withLoginCheck(User);
            
            <UserWithLoginCheck isLoggedIn={false} />
            ```
            
    - Virtual DOM in React & 4 Imp features of React
        
        Virtual DOM ek JS **Object** hai jo ki browser ki memory (RAM) me store hota hai. Virtual DOM is similar to Actual DOM created by browser. Jab bhi UI me koi changes hota hai toh React new Virtual DOM banata hai aur purane Virtual DOM se comparison karta hai. Dono ke coparisoon ke baad jo bhi changed hote hai sirf wo hi changes actual DOM me efficiently kiye jate hai. The whole actual DOM is not manipulated in this way only the parts which are changed.
        
        > **WHY Actual DOM is not efficient to be Completely Updated every time ? :-** Recalculating the whole page CSS and then recreating the layout is taxing and React finds a way to avoid it
        > 
        
        4 Important Features of React
        
        - Virtual DOM
        - Component based
        - View Oriented - Its primary focus is on managing and rendering the visual user interface (UI) of an application
        - Unidirectional Data Flow - Data passes from top component to bottom component
    - Lifecycle methods in class components and the equivalent hooks in functional components.
        - **componentDidMount**() - useEffect with  empty [ ] array
        - **componentDidUpdate**() - useEffect with dependency in the array
        - **componentWillUnmount**() - useEffect with a return cleanup function
    - JSX: Explain JSX and why it’s used in React.
        
        JavaScript XML
        
        Using JSX (JavaScript XML) we do not have to use appendChild() or createElement() to create HTML code. We can simply use HTML looking like tags to directly write our frontend code and use JS functions & React elements (hooks, state etc.)
        
    - Reconciliation & Diffing algorithm (Managing Changes in React)
        
        **Reconciliation** is the process that runs whenever there is a state change or initial loading of the app. It involves
        
        1. Creating of a new Virtual DOM Tree.
        2. Running Diffing Algo. - **Diffing** is algorithm to the measure of the difference between the 2 Virtual DOMs created by the React.
        3. Creating a Fiber Tree - It is a tree structure made out of the differences observed and each fiber consists of the component and its update.
        4. React Updates ko prioritize bhi karta hai according to user interactions kyonki wo view oriented hai aur jo changes user ko zyada effect krte hai unko priority milti hai. It is new update of React (16+) it improves freezing of the app during update & improves responsiveness
        5. Commits the changes
    - What is React Fiber
        
        React 16 ke baad ka update hai ye. Fiber Tree is made out of the differences observed b/w two V-DOMs and each fiber consists of the component, its update & additional information about updates.
        
        React Updates ko prioritize karta hai according to user interactions kyonki wo view oriented hai aur jo changes user ko zyada effect krte hai unko priority milti hai. It improves freezing of the app during update & improves responsiveness.
        
        - Benefits - Smooth Updates, Improves responsiveness, makes app fast
    - Props vs State in React
        
        Props are the read-only data passed on from one Component to another in a unidirectional flow Parent to Child. They work similar to like arguments passed in a JS function.
        
        State is an object that stores data and allows to change it over time. In Function based React useState() is commonly used to manage and change state.
        
    - Hooks in React
        
        Hooks are the functions that “hooks” into a React component **state** and helps us to manage & modify a **state or a lifecycle event.** 
        
    - Custom Hook? What, Where, How ?
        
        Existing Hooks aur functions ko use karke ham ek ‘use’ se shuru hone wala component bana sakte hai. Ye component ham apne istemal aur convenience ke liye bana sakte hai 
        
        Eg - 
        
        ```jsx
        import { useState, useEffect } from "react";
        
        const useFetch = (url) => {
          const [data, setData] = useState(null);
        
          useEffect(() => {
            fetch(url)
              .then((res) => res.json())
              .then((data) => setData(data));
          }, [url]);
        
          return [data];
        };
        
        export default useFetch;
        ```
        
        ```jsx
        import ReactDOM from "react-dom/client";
        import useFetch from "./useFetch";
        
        const Home = () => {
          const [data] = useFetch("https://jsonplaceholder.typicode.com/todos");
        
          return (
            <>
              {data &&
                data.map((item) => {
                  return <p key={item.id}>{item.title}</p>;
                })}
            </>
          );
        };
        
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<Home />);
        ```
        
    - Explain common hooks: `useState`, `useEffect`, `useMemo`, `useCallback`, `useContext`, `useRef`, `useReducer`
        
        
    - How would you manage state with `useReducer` instead of `useState`?
    - S.S.R vs C.S.R & how can React app be made S.S.R
    - Shallow Copy & Deep Copy
    - **Render Props**: Describe the render props pattern and how it compares to HOCs.
    - Suspense and Lazy Loading? What, When, How
        - Suspense ek tarika hai React me jis se ham koi async task (data fetch) ya fir UI loading ke dauran ek fallback UI dikha sakte hai. Loading state dikha sakte hai.
        - Lazy loading ek concept hai jis se ki ham koi expensive import ko delay se load kar sakte hai taki hamara app faster ho sake. React.lazy(()⇒import component from “./file”)
        
        ```jsx
        const LazyComponent = React.lazy(() => import('./MyComponent'));
        
        function App() {
          return (
            <Suspense fallback={<div>Loading...</div>}>
              <LazyComponent />
            </Suspense>
          );
        }
        ```
        
    - **Error Boundaries**: How do error boundaries work in React? Can they be used with hooks?
    - Memoization ? Explain the use of `memo`, `useMemo`, and `useCallback`.
        
        Memoization is a technique used in computer science to speed up the execution of recursive or computationally expensive functions by caching the results of function calls and returning the cached results when the same inputs occur again.
        
        > Caching - process of storing data in a temporary location, called a cache.
        > 
        
        ### React.memo
        
        To refrain from unnecessarily re-rendering a component we use memo. This basically caches the component and only re-renders it if its props (handleClick & value) have changed.
        
        ```jsx
        const App = () => {
          const [count, setCount] = useState(0);
          const [value, setValue] = useState("");
        
          const handleClick = () => {
            setValue("Kunal");
          };
          return (
            <div className="App">
              <button onClick={() => setCount(count + 1)}>Increment Count</button>
              <p>Count: {count}</p>
              <p>Value: {value}</p>
              <SlowComponent handleClick={handleClick} /> 
              {/*This is a slow operation*/}
            </div>
          );
        };
        
        const SlowComponent = React.memo(({ handleClick, value }) => {
        
          // Intentially making the component slow
          for (let i = 0; i < 1000000000; i++) {}
        
          return (
            <div>
              <h1>Slow Component</h1>
              <button onClick={handleClick}>Click Me</button>
        
            </div>
          );
        });
        ```
        
        - useMemo
            
            It caches the **return value** of a function and return the same value if the input parameters of the function have not been changed.
            
            ```jsx
            const value = useMemo(expensiveFunction, [dependencyArray])
            ```
            
        
        - useCallback
            
             `useCallback` hook memoizes the function itself, not its return value. `useMemo` caches the functions return value so that the function need not execute again. `useCallback` caches the function definition or the function reference.
            
            In the above code <SlowComponent/> is slow but handleClick function remains the same (also we do not need its output value). We can useCallback here to optimise handleClick
            
            ```jsx
             const handleClick = useCallback(() => {
                setValue("Kunal");
              }, [value, setValue]);
            ```
            
    - State Management? Context API ? Redux ?
    - Redux Thunk? What, Where, How ?
        
        API Calls w/o Redux Async Thunk (plain Redux sample code)
        
        ```jsx
        // Actions
        const fetchProductsStart = () => ({ type: 'FETCH_PRODUCTS_START' });
        const fetchProductsSuccess = (products) => ({
          type: 'FETCH_PRODUCTS_SUCCESS',
          payload: products,
        });
        const fetchProductsFailure = (error) => ({
          type: 'FETCH_PRODUCTS_FAILURE',
          payload: error,
        });
        
        // Reducer
        const initialState = {
          items: [],
          loading: false,
          error: null,
        };
        
        const productsReducer = (state = initialState, action) => {
          switch (action.type) {
            case 'FETCH_PRODUCTS_START':
              return { ...state, loading: true, error: null };
            case 'FETCH_PRODUCTS_SUCCESS':
              return { ...state, loading: false, items: action.payload };
            case 'FETCH_PRODUCTS_FAILURE':
              return { ...state, loading: false, error: action.payload };
            default:
              return state;
          }
        };
        
        // API Call (in a component or service)
        export const fetchProducts = () => {
          return async (dispatch) => {
            dispatch(fetchProductsStart());
            try {
              const response = await fetch('https://api.example.com/products');
              const data = await response.json();
              dispatch(fetchProductsSuccess(data));
            } catch (error) {
              dispatch(fetchProductsFailure(error.message));
            }
          };
        };
        ```
        
        API Call with Redux Async Thunk
        
        ```jsx
        import { createAsyncThunk, createSlice } from '@reduxjs/toolkit';
        
        export const fetchProducts = createAsyncThunk(
          'products/fetchProducts',
          async () => {
            const response = await fetch('https://api.example.com/products');
            return response.json();
          }
        );
        
        const productsSlice = createSlice({
          name: 'products',
          initialState: { items: [], loading: false, error: null },
          reducers: {},
          extraReducers: (builder) => {
            builder
              .addCase(fetchProducts.pending, (state) => {
                state.loading = true;
                state.error = null;
              })
              .addCase(fetchProducts.fulfilled, (state, action) => {
                state.loading = false;
                state.items = action.payload;
              })
              .addCase(fetchProducts.rejected, (state, action) => {
                state.loading = false;
                state.error = action.error.message;
              });
          },
        });
        ```
        
    - Code Splitting ? What, Where, How ?
    - React 18 updates
        - Concurrent Rendering
            
            Multiple UI renders ko side by side render kar sakta hai React jis se ki UI smooth ho gyi hai aur lag nhi karti complex UI ya expensive state change karte time render karte time
            
        - Automatic Batching for state updates
            
            State updates sari ek hi render me hoti hai chahe wo async state update hi kyo n ho.
            
        - Into of Transitions
            
            Low priority updates jo ki background me bhi update ho sakti hai bina main UI ko block kare. Low priority queue me bhej deta hai ye in computations ko aur UI ko bad me render kara deta hai bina screen freeze kiye. 
            
            ```jsx
            import { useState, useTransition } from 'react';
            
            function App() {
              const [isPending, startTransition] = useTransition();
              const [input, setInput] = useState('');
              const [list, setList] = useState([]);
            
              const handleChange = (e) => {
                setInput(e.target.value);
            
                // Background update
                startTransition(() => {
                  const newList = Array(20000)
                    .fill(e.target.value)
                    .map((_, i) => `${e.target.value} ${i}`);
                  setList(newList);
                });
              };
            
              return (
                <div>
                  <input value={input} onChange={handleChange} />
                  {isPending && <div>Loading...</div>}
                  <ul>{list.map((item, index) => <li key={index}>{item}</li>)}</ul>
                </div>
              );
            }
            ```
            
- React-Native
    - Which JS Engine React Native uses ?
        
        Hermes is default JS engine engine for React Native apps and is supported for both Android & IoS. JavaScriptCore was the default engine before this which is sometimes used for older apps. 
        
    - What are Threads
        
        RN Code ke pure task ya runtime ko threads me divide kia jata hai (In React, you don't directly deal with threads). There are 3 main types of threads in React Native.
        
        - Main Thread (UI Thread)
            
            Ye Thread sirf UI rendering ya re-rendering ke liye use hoti hai.
            
        - Shadow Thread
            
            UI render hone se phele jo Canvas(screen) ki calculations hai border-radius, height, width etc. unko ye thread calculate karti hai 
            
        - JS Thread
            
            JS code ko compile katra hai ye thread..
            
- Data Structures
    - Linked list
        
        ```jsx
        // single node of the list
        class Node {
        	constructor(value){
        		this.value=value
        		this.next=null  //it will be set when list is made
        		this.prev=null
        	}
        }
        
        // the list
        class DoublyLinkedList{
        	constructor(){
        		this.head = null
        	}
        	add(value){
        	let newNode = new Node(value)
        		if(!this.head){
        			this.head = newNode
        			return
        		}
        		//now if there is no head we will traverse the -
        		//- whole list to find the current spot
        		let current = this.head
        		while(current.next){
        			current = current.next
        		}
        		current.next = newNode
        		newNode.prev = current
        	}
        }
        ```
