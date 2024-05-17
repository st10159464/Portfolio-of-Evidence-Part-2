# Portfolio-of-Evidence-Part-2
kantan board with unit testing
Programming 1A 
Module code: PROG5121/d/p
Portfolio of Evidence Part 2
Richard Anthony Wimbush  ST10159464

import javax.swing.JOptionPane;

public class Task {
    private String taskName;
    private int taskNumber;
    private String taskDescription;
    private String developerDetails;
    private int taskDuration;
    private String taskID;
    private String taskStatus;

    public Task(String taskName, String taskDescription, String developerDetails, int taskDuration, String taskStatus) {
        this.taskName = taskName;
        this.taskDescription = taskDescription;
        this.developerDetails = developerDetails;
        this.taskDuration = taskDuration;
        this.taskStatus = taskStatus;
    }

    public boolean checkTaskDescription() {
        return taskDescription.length() <= 50;
    }

    public String createTaskID() {
        String firstTwoLetters = taskName.substring(0, 2).toUpperCase();
        String lastThreeLetters = developerDetails.substring(developerDetails.length() - 3).toUpperCase();
        taskID = firstTwoLetters + ":" + taskNumber + ":" + lastThreeLetters;
        return taskID;
    }

    public String printTaskDetails() {
        return "Task Status: " + taskStatus + "\nDeveloper Details: " + developerDetails + "\nTask Number: " + taskNumber +
                "\nTask Name: " + taskName + "\nTask Description: " + taskDescription + "\nTask ID: " + taskID +
                "\nTask Duration: " + taskDuration + " hours";
    }

    public static void main(String[] args) {
        int numTasks = Integer.parseInt(JOptionPane.showInputDialog("Enter the number of tasks: "));
        int totalHours = 0;

        for (int i = 0; i < numTasks; i++) {
            String taskName = JOptionPane.showInputDialog("Enter Task Name for Task " + (i + 1) + ": ");
            String taskDescription = JOptionPane.showInputDialog("Enter Task Description for Task " + (i + 1) + ": ");
            String developerDetails = JOptionPane.showInputDialog("Enter Developer Details for Task " + (i + 1) + ": ");
            int taskDuration = Integer.parseInt(JOptionPane.showInputDialog("Enter Task Duration for Task " + (i + 1) + " in hours: "));
            String taskStatus = JOptionPane.showInputDialog("Enter Task Status (To Do, Done, Doing) for Task " + (i + 1) + ": ");

            Task task = new Task(taskName, taskDescription, developerDetails, taskDuration, taskStatus);
            task.taskNumber = i; // Auto-generate task number

            if (!task.checkTaskDescription()) {
                JOptionPane.showMessageDialog(null, "Please enter a task description of less than 50 characters");
                i--; // Allow user to re-enter task details
                continue;
            }

            task.taskID = task.createTaskID();
            totalHours += taskDuration;

            JOptionPane.showMessageDialog(null, "Task successfully captured:\n\n" + task.printTaskDetails());
        }

        JOptionPane.showMessageDialog(null, "Total hours across all tasks: " + totalHours);
    }
}

import javax.swing.JOptionPane;

public class Task {
    private String taskName;
    private int taskNumber;
    private String taskDescription;
    private String developerDetails;
    private int taskDuration;
    private String taskID;
    private String taskStatus;

    public Task(String taskName, String taskDescription, String developerDetails, int taskDuration, String taskStatus) {
        this.taskName = taskName;
        this.taskDescription = taskDescription;
        this.developerDetails = developerDetails;
        this.taskDuration = taskDuration;
        this.taskStatus = taskStatus;
    }

    public boolean checkTaskDescription() {
        return taskDescription.length() <= 50;
    }

    public String createTaskID() {
        String firstTwoLetters = taskName.substring(0, 2).toUpperCase();
        String lastThreeLetters = developerDetails.substring(developerDetails.length() - 3).toUpperCase();
        taskID = firstTwoLetters + ":" + taskNumber + ":" + lastThreeLetters;
        return taskID;
    }

    public String printTaskDetails() {
        return "Task Status: " + taskStatus + "\nDeveloper Details: " + developerDetails + "\nTask Number: " + taskNumber +
                "\nTask Name: " + taskName + "\nTask Description: " + taskDescription + "\nTask ID: " + taskID +
                "\nTask Duration: " + taskDuration + " hours";
    }

    public static void main(String[] args) {
        int numTasks = Integer.parseInt(JOptionPane.showInputDialog("Enter the number of tasks: "));
        int totalHours = 0;

        for (int i = 0; i < numTasks; i++) {
            String taskName = JOptionPane.showInputDialog("Enter Task Name for Task " + (i + 1) + ": ");
            String taskDescription = JOptionPane.showInputDialog("Enter Task Description for Task " + (i + 1) + ": ");
            String developerDetails = JOptionPane.showInputDialog("Enter Developer Details for Task " + (i + 1) + ": ");
            int taskDuration = Integer.parseInt(JOptionPane.showInputDialog("Enter Task Duration for Task " + (i + 1) + " in hours: "));
            String taskStatus = JOptionPane.showInputDialog("Enter Task Status (To Do, Done, Doing) for Task " + (i + 1) + ": ");

            Task task = new Task(taskName, taskDescription, developerDetails, taskDuration, taskStatus);
            task.taskNumber = i; // Auto-generate task number

            if (!task.checkTaskDescription()) {
                JOptionPane.showMessageDialog(null, "Please enter a task description of less than 50 characters");
                i--; // Allow user to re-enter task details
                continue;
            }

            task.taskID = task.createTaskID();
            totalHours += taskDuration;

            JOptionPane.showMessageDialog(null, "Task successfully captured:\n\n" + task.printTaskDetails());
        }

        JOptionPane.showMessageDialog(null, "Total hours across all tasks: " + totalHours);
    }
}
