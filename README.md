from flask import Flask, render_template, request, redirect, jsonify

app = Flask(__name__)

# In-memory database (for demo purposes)
tasks = []

@app.route('/')
def index():
    return render_template('index.html', tasks=tasks)

@app.route('/add', methods=['POST'])
def add_task():
    task = request.form.get('task')
    if task:
        tasks.append({'id': len(tasks) + 1, 'task': task, 'done': False})
    return redirect('/')

@app.route('/delete/<int:task_id>', methods=['POST'])
def delete_task(task_id):
    global tasks
    tasks = [task for task in tasks if task['id'] != task_id]
    return redirect('/')

@app.route('/toggle/<int:task_id>', methods=['POST'])
def toggle_task(task_id):
    for task in tasks:
        if task['id'] == task_id:
            task['done'] = not task['done']
    return redirect('/')

if __name__ == '__main__':
    app.run(debug=True)