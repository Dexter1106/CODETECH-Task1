<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List App</title>
    <style>
        /* Reset some basic styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #153677, #4e085f);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background: #fff;
            padding: 40px 30px 70px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(73, 73, 73, 0.1);
            width: 100%;
            max-width: 540px;
            margin: 100px auto 20px;
            background-image: url('https://marketplace.canva.com/EAFuKIbGJJg/1/0/900w/canva-green-watercolor-instagram-story-background-MpipxzoqTl0.jpg');
        }

        h1 {
            text-align: center;
            margin-bottom: 20px;
            color: #333;
        }

        form {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }

        #todo-input {
            flex: 1;
            padding: 10px;
            border: 2px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
            margin-right: 10px;
        }

        button {
            padding: 10px 20px;
            border: none;
            background: #007bff;
            color: #fff;
            font-size: 16px;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        button:hover {
            background: #0056b3;
        }

        ul {
            list-style: none;
        }

        li {
            padding: 10px;
            border-bottom: 1px solid #ddd;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: background 0.3s ease;
        }

        li:last-child {
            border-bottom: none;
        }

        li:hover {
            background: #f9f9f9;
        }

        li span {
            flex: 1;
        }

        li button {
            background: #dc3545;
            color: #fff;
            border: none;
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        li button:hover {
            background: #c82333;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <form id="todo-form">
            <input type="text" id="todo-input" placeholder="Add a new task">
            <button type="submit">Add</button>
        </form>
        <ul id="todo-list"></ul>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const form = document.getElementById('todo-form');
            const input = document.getElementById('todo-input');
            const todoList = document.getElementById('todo-list');

            form.addEventListener('submit', (event) => {
                event.preventDefault();
                addTodo();
            });

            function addTodo() {
                const task = input.value.trim();
                if (task !== '') {
                    const li = document.createElement('li');
                    li.textContent = task;
                    const removeButton = document.createElement('button');
                    removeButton.textContent = 'Remove';
                    removeButton.addEventListener('click', () => {
                        li.remove();
                    });
                    li.appendChild(removeButton);
                    todoList.appendChild(li);
                    input.value = '';
                }
            }
        });
    </script>
</body>
</html>
