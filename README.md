# DynamicTaskMaster: Real-Time Scheduler Suite

The Real-Time Task Scheduler GUI is a Python utility offering an interactive interface for task management and scheduling, employing a variety of real-time scheduling algorithms.

## System Architecture Diagram

+---------------------+            +-------------+
|   SchedulerGUI     |            |     Task    |
|--------------------|            |-------------|
|                     \          /               |
|   +--------------+   \ contains /    +-------+|
|   | add_task()   |---\------->/-----| get_  ||
|   +--------------+    \            | name()||
|                       \           |-------+--|
|   +--------------+     \contains /+-------+  |
|   | remove_task()|------->-----/ |get_   |  |
|   +--------------+     /         |arrival|  |
|                       /          |_time()|  |
|   +--------------+    /           +-------+  |
|   | edit_task()  |-->/ contains              |
|   +--------------+   /            +-------+  |
|                       \           |get_   |  |
|   +--------------+     \contains /|deadline|  |
|   | save_tasks() |------->-----/ |_()    |  |
|   +--------------+     /          +-------+  |
|                       /                      |
|   +--------------+   /                       |
|   | load_tasks() |---                        |
|   +--------------+                          |
|                                              |
|   +--------------+                          |
|   | schedule_    |                          |
|   |  tasks()     |                          |
|   +--------------+                          |
|                                              |
|   +--------------+                          |
|   | plot_gantt   |                          |
|   | _chart()     |                          |
|   +--------------+                          |
|                                              |
|   +--------------+                          |
|   | view_task    |                          |
|   | _details()   |                          |
|   +--------------+                          |
+---------------------+            +-------------+


## Key Features

- **Task Administration**: Seamlessly add, modify, and delete tasks via an intuitive interface. Each task encompasses essential attributes such as name, arrival time, and deadline.

- **Diverse Scheduling Algorithms**: Select from a range of scheduling algorithms to orchestrate task scheduling, tailored to meet specific requirements:
  - **Earliest Deadline First (EDF)**: Prioritizes tasks based on their deadlines, ensuring tasks with the earliest deadlines are executed first to minimize deadline breaches.
  
  - **Rate-Monotonic Scheduling (RMS)**: Prioritizes tasks according to their periods, with shorter period tasks receiving higher priority. RMS is ideal for tasks with fixed execution durations and periodicity.
  
  - **First-Come, First-Served (FCFS)**: Executes tasks in the order of their arrival, with the earliest arriving task taking precedence.
  
  - **Shortest Job Next (SJN)**: Executes the shortest task available in the ready queue first, reducing waiting time by prioritizing shorter tasks.
  
  - **Round Robin (RR)**: Allocates fixed time slices (quantum) to each task in a cyclic fashion. Tasks execute for a fixed quantum before being moved to the end of the ready queue.
  
  - **Multilevel Queue (MLQ)**: Segregates tasks into multiple priority-based queues, each employing its scheduling algorithm.
  
  - **Multilevel Feedback Queue (MLFQ)**: Similar to MLQ but incorporates dynamic priority adjustments, allowing tasks to move between queues based on their behavior and resource needs.
  
  - **Priority Scheduling**: Assigns priorities to tasks based on predefined criteria, ensuring higher priority tasks are executed first.
  

- **Comprehensive Task Details**: Access detailed insights into tasks, including their current status, time remaining until the deadline, and any potential scheduling conflicts.

- **File Management**: Facilitates seamless task list storage and retrieval through file I/O operations, allowing tasks to be saved to and loaded from files in a simple text format for enhanced data management and future utilization.

- **Interactive Gantt Chart**: Offers a visual representation of scheduling outcomes via Gantt charts, enabling users to grasp task scheduling and resource utilization effortlessly.

## Installation Steps

1. **Clone the Repository**: Clone or download the repository to your local machine.

   ```
   git clone https://github.com/parth-5097/dynamic-task-master.git
   ```

2. **Install Dependencies**: Ensure Python is installed (preferably Python 3.x) and install necessary dependencies using pip.

   ```
   pip install matplotlib
   ```

## Usage Guidelines

1. **Launch the Application**: Navigate to the project directory and execute the `main.py` file using Python.

   ```
   cd real-time-task-scheduler
   python main.py
   ```

2. **Task Management**: Utilize the graphical interface to manage tasks efficiently, including adding, editing, removing, saving, and loading tasks. Input task specifics such as name, arrival time, and deadline.

3. **Algorithm Selection**: Choose the desired scheduling algorithm from the dropdown menu. Available options encompass Earliest Deadline First (EDF), Rate-Monotonic Scheduling (RMS), First-Come, First-Served (FCFS), Shortest Job Next (SJN), Round Robin (RR), Multilevel Queue (MLQ), Multilevel Feedback Queue (MLFQ), and Priority Scheduling.

4. **Task Scheduling**: Click the "Schedule" button to schedule tasks utilizing the selected algorithm. The output will be presented in the text area, delineating scheduling specifics and any missed deadlines.

5. **Gantt Chart Visualization**: The application generates a Gantt chart to visually represent scheduling outcomes, offering insights into task execution and resource utilization.