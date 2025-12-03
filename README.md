# Project-8
To do list
#include <stdio.h>
#include <string.h>

int main() {
    char tasks[50][100];
    int choice, count = 0;

    while (1) {
        printf("\n--- To-Do List ---\n");
        printf("1. Add Task\n");
        printf("2. View Tasks\n");
        printf("3. Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);
        getchar(); // clear newline

        if (choice == 1) {
            printf("Enter task: ");
            fgets(tasks[count], 100, stdin);
            tasks[count][strcspn(tasks[count], "\n")] = '\0';
            count++;
            printf("Task added!\n");
        }

        else if (choice == 2) {
            printf("\n--- Your Tasks ---\n");
            for (int i = 0; i < count; i++) {
                printf("%d. %s\n", i + 1, tasks[i]);
            }
        }

        else if (choice == 3) {
            printf("Exiting...\n");
            break;
        }

        else {
            printf("Invalid choice! Try again.\n");
        }
    }

    return 0;
}
