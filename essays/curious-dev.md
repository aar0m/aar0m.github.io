---
layout: essay
type: essay
title: "How curiosity killed the developer"
# All dates must be YYYY-MM-DD format!
date: 2025-01-30
published: true
labels:
  - Questions
  - Answers
  - StackOverflow
---

<img width="100%" src="../img/essays-img/questions.png" class="pb-3">

Throughout the life cycle of various programs and projects, both experienced and newbie programmers alike eventually encounter issues that they simply do not know the answer to. This is where the distinction between experienced and newbie is exposed; experienced programmers embark on a troubleshooting process that involves due diligence and asking smart questions, whilst newbie programmers may feel inclined to immediately ask for help.

Though understandable, this newbie instinct to _ask questions first, think later_ is unfortunately what leads to a prevalent (but very real) cause of death for most projects and programs: **death by curiosity.**

## An autopsy

To elaborate, death by curiosity occurs when programmers, developers, or hackers impatiently attempt to find answers without performing a troubleshooting process. Such a scenario leads to a rushed, incomprehensible query that is less likely to be responded to. At best, this leads to receiving a helpful answer with a side of shaming or online ridicule. At worst, development is either delayed or outright canceled due to no responses whatsoever, hence a "death" of a project.

Consider the following example of [death by curiosity from StackOverflow](https://stackoverflow.com/questions/79401719/getting-data-map-is-not-a-function), a forum site consisting of user-generated queries and responses. 

```
Q: Getting data.map is not a function

I'm getting error todos.map is not a function, only that line gives error if I remove the div of the mapping then the code works fine. All the other functions and components works fine, then why is this not working.

Please someone explain this, todos is an array then why the mapping is not working here.
```

Preceding the paragraphs is plain-text code from the developer program:

```javascript
import { useState, useEffect } from "react";
import { TodoProvider } from "./contexts/TodoContext";
import TodoForm from "./components/TodoForm";
import TodoItem from "./components/TodoItem";

function App() {
  const [todos, setTodos] = useState([]);

  const addTodo = (todo) => {
    setTodos((prev) => [{ id: Date.now(), ...todo }, ...prev]);
  };

  const updateTodo = (id, todo) => {
    setTodos((prev) =>
      prev.map((prevTodo) => (prevTodo.id === id ? todo : prevTodo))
    );
  };

  const deleteTodo = (id) => {
    setTodos((prev) => prev.filter((prevTodo) => prevTodo.id !== id));
  };

  const toggleComplete = (id) => {
    setTodos((prev) =>
      prev.map((prevtodo) =>
        prevtodo.id === id
          ? { ...prevtodo, completed: !prevtodo.completed }
          : prevtodo
      )
    );
  };

  useEffect(() => {
    const todosLocal = JSON.parse(localStorage.getItem("todos"));

    if (todosLocal && todosLocal.length > 0) {
      setTodos(todosLocal);
    }
  }, []);

  useEffect(() => {
    localStorage.setItem("todos", JSON.stringify("todos"));
  }, [todos]);

  return (
    <TodoProvider
      value={{ todos, addTodo, updateTodo, deleteTodo, toggleComplete }}
    >
      <h2 className="text-center text-3xl font-bold mt-1">Hello</h2>
      <div className="bg-[#172842] min-h-screen py-8">
        <div className="w-full max-w-2xl mx-auto shadow-md rounded-lg px-4 py-3 text-white">
          <h1 className="text-2xl font-bold text-center mb-8 mt-2">
            Manage Your Todos
          </h1>
          <div className="mb-4">
            {/* Todo form goes here */}
            <TodoForm />
          </div>
          <div className="flex flex-wrap gap-y-3">
            {todos.map((todo) => (
              <div key={todo.id} className="w-full">
                <TodoItem todo={todo} />
              </div>
            ))}
          </div>
        </div>
      </div>
    </TodoProvider>
  );
}

export default App;
```

This example of death by curiosity can be better described as a case study of **how to not properly ask questions**. For a better understanding, I will review the post from top to bottom.

- **Title:** The title of the question is vague, despite using the 'javascript' tag. The question title, **'Getting data.map is not a function'**,provides no insight into the problem being encountered and poses more confusion for readers, requiring more effort to be put into understanding the problem than discussing a solution.

- **Code:** The code is the first item posted; though it is well-formatted, this practice can be overwhelming and confusing due to the lack of context. If I were an expert attempting to answer this question, I would not understand much at this point aside from "getting data.map is not a function". Currently, the code provides no substance because its functionality is not explicitly explained by the user.

- **Content:** Lastly, the content of the question. Similar to the point made regarding code, the developer provides little, if any, context about their problem. They simply reiterate that their program is not working without any specificities about the misbehaving code or even what the program is expected to do.

Therefore, this question clearly demonstrates that the developer did not make sincere efforts to resolve their issue diligently and simply sought a quick fix. This is further supported by the solution given:

```
A: JSON.stringify("todos") 👈 there's your problem. Remove the quotes 
```

The problem was a basic syntax error. Luckily, the developer was able to make like a bandit and retrieve a relatively quick fix to their issues and "cheat death". However, not all developers are lucky and may idly wait days, weeks, months, or even longer for a response. What's worse is that not all responses are guaranteed to be helpful if the questions being asked are not sufficiently informative, organized, or "smart".

## Surviving curiosity as a developer

Posing a question that is informative and organized, also known as a _smart question_ can lead to thought-provoking discussion, an increase in both response quality and quantity, as well as a chance to problem-solve alongside fellow developers. This set of outcomes prevent projects from becoming stale and, in turn, decreases the likelihood of developers experiencing death by curiosity.

However, asking a smart question is not a simple task. The first step to asking a smart question is to independently troubleshoot the issue at hand. To do this, developers must build and strengthen a skill (or tolerance) to reading. This is because many coding, program, and project issues can be resolved with some time, elbow grease, and a decent reading comprehension. Whether it is a manual, proper web/forum searches, or code itself, the ability to discern main ideas from dense bodies of text and efficiently scan data to find relevant text is a skill applicable in many settings, and perhaps, life in general.

This being said, a smart question encompasses this effort of performing due diligence and even more. I am specfically referring to the content of a smart question. In this case, a [smart question from StackOverflow](https://stackoverflow.com/questions/43871637/no-access-control-allow-origin-header-is-present-on-the-requested-resource-whe) will be reviewed:

```
Q: No 'Access-Control-Allow-Origin' header is present on the requested resource—when trying to get data from a REST API

I'm trying to fetch some data from the REST API of HP Alm. It works pretty well with a small curl script—I get my data.

Now doing that with JavaScript, fetch and ES6 (more or less) seems to be a bigger issue. I keep getting this error message: [erorr message omitted from essay]

I understand that this is because I am trying to fetch that data from within my localhost and the solution should be using Cross-Origin Resource Sharing (CORS). I thought I actually did that, but somehow it either ignores what I write in the header or the problem is something else.

So, is there an implementation issue? Am I doing it wrong? I can't check the server logs unfortunately. I'm really a bit stuck here.

I am using Chrome. I also tried using that Chrome CORS Plugin, but then I am getting another error message: [error message omitted from essay]
```

```javascript
function performSignIn() {

  let headers = new Headers();

  headers.append('Content-Type', 'application/json');
  headers.append('Accept', 'application/json');

  headers.append('Access-Control-Allow-Origin', 'http://localhost:3000');
  headers.append('Access-Control-Allow-Credentials', 'true');

  headers.append('GET', 'POST', 'OPTIONS');

  headers.append('Authorization', 'Basic ' + base64.encode(username + ":" + password));

  fetch(sign_in, {
      //mode: 'no-cors',
      credentials: 'include',
      method: 'POST',
      headers: headers
    })
    .then(response => response.json())
    .then(json => console.log(json))
    .catch(error => console.log('Authorization failed : ' + error.message));
}
```

Similar to the prior example, the positive qualities of a smart question will be revealed from top to bottom.

- **Title:** The title is cleanly divided into two parts: the problem ('No 'Access-Control-Allow-Origin' header is present on the requested resource') and the intended goal  ('—when trying to get data from a REST API'). Though not strictly abiding by what is expected from a smart question, the header is both concise and descriptive enough for potential readers to understand a simplified version of the problem being encountered, allowing for ideation to occur much sooner.

- **Content:** The content of the question is deeply informative. First, it reiterates the main goal of the program, integral to troubleshooting. Then, the content provides error messages relevant to the problem encountered, alongside the development tools and environment being used. Both types of information can help readers better understand what the developer is seeing and narrows the scope of the problem from being too vague and general to answer. Moreover, the content reflects that the developer has a deep understanding of what they want their program to do and that they had performed their due diligence of reading documentation, while attempting to independently fix the problem. This is apparent through their mention of supposedly trying a solution, as shown below. As I have covered, attempting to troubleshoot is integral to asking a _good_ smart question that is likely to receive _helpful_ responses.

```
"I understand that this is because I am trying to fetch that data from within my localhost and the solution should be using Cross-Origin Resource Sharing (CORS). I thought I actually did that"
```

- **Code:** Lastly, the code provided after the context is given, allowing readers to efficiently parse the code without the hassle of trying to figure out its main functionality.

In tandem, these qualities allow for the question asked to be precise in regards to the problem encountered. Surely enough, the developer encountered a [descriptive, smart answer](https://stackoverflow.com/a/43881141), one so descriptive and helpful that it was divided into three sections. 

Neither the specifics nor complexity of the solution are the main focus. Rather, it is to distinctly point out how asking a smart question can lead to descripitive, thorough, and helpful answers, completely avoiding death by curiosity altogether.

## Conclusion

Thus, we have shown that death by curiosity does not have to be a signifier of a newbie programmer. In essence, death by curiosity is a pitfall that lazier developers can fall into, seeking quick and easy fixes for what they perceive to be roadblocks. This leads to crudely-asked, vague, and confusing questions that have no regard for the problem being encountered, just a hunger for solutions that will satisfy the problem. 

However, curiosity can be reframed as a tool for making stronger programmers, developers, and hackers. Opposite of roadblocks, errors are more akin to learning opportunities, a capability that can only be exposed by those willing to sincerely engage with and troubleshoot their errors independently and ask 'smart' questions---questions that are concise about the developer's goals, the issue they are experiencing, specificities of their development environment, and all relevant information.