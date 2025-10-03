# Code-Blocks-Experiment-2

📡 Implementation of Go-Back-N Protocol – Selective Repeat

🎯 Aim

To write and execute a program for the Go-Back-N protocol using the Selective Repeat technique.

🛠️ Equipments Required

• 	Personal Computer

• 	Turbo C Compiler

📋 Procedure
1. 	Connect two computers in a Wired/Wireless LAN.
2. 	Ensure both computers are on the same network and can ping each other.
3. 	Open a new C file in Code::Blocks or any C IDE and type the program.
4. 	Navigate to:
Project -> Properties -> Project Build Options -> Linker Settings
Add: netproto and pthread
5. 	Execute the program on both server and client machines.
6. 	Enter the following:
• 	IP address of the remote machine
• 	Port address of both local and remote machines
• 	Error rate
7. 	Choose the file and verify the Go-Back-N protocol operation.

💻 Program
```
#include <stdio.h>

int main() {
    int i, j, n;
    printf("GO BACK N ARQ\n");
    printf("Enter number of frames: ");
    scanf("%d", &n);

    char frame[n][10];  // each frame content (max length 9 chars)

    for (i = 0; i < n; i++) {
        printf("Content for frame %d: ", i + 1);
        scanf("%s", frame[i]);
    }

    printf("Enter frame number with no ACK: ");
    scanf("%d", &j);

    for (i = 0; i < n; i++) {
        if (i + 1 != j) {
            printf("\nSending frame %d\nFRAME ACKNOWLEDGED...\n", i + 1);
        }
    }

    if (j >= 1 && j <= n) {
        printf("No Acknowledgement for frame %d...\n", j);
        printf("Resending... Content from frame %d: %s\n\n", j, frame[j - 1]);
        printf("\nSending frame %d\nFRAME ACKNOWLEDGED...\n", j);
    }

    printf("\n\nALL FRAMES RECEIVED SUCCESSFULLY\n\n");
    return 0;
}
```

 
Output

<img width="1917" height="1075" alt="image" src="https://github.com/user-attachments/assets/2da064b4-547f-4a65-ab03-3de4e1ae07ff" />

✅ Result

Thus, the Go-Back-N protocol using Selective Repeat was successfully implemented and verified.
