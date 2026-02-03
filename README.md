# Digital-Clock-New-Year-Countdown-C-
This project is a terminal-based digital clock written in C that displays the current local time in real time. The program continuously updates the clock using system time functions and formats the output to resemble a digital clock display.

A special feature of this project is a built-in New Year trigger. When the system time reaches 12:00 AM on January 1st, the program automatically prints a celebratory “HAPPY NEW YEAR” message to the terminal.

Key Features:
Real-time clock display using system time
Continuous screen updates using loops
Conditional logic to detect a specific date and time
Cleanly formatted terminal output

Concepts Used:
time.h and system time functions
Loops and conditional statements
Formatted output
Program flow control


    #include <stdio.h>
    #include <time.h>
    #include <stdbool.h>
    #include <unistd.h>
    
    int main(){

    time_t rawtime = 0; 
    struct tm *pTime = NULL;
    bool isRunning = true;

    printf("DIGITAL ClOCK\n");

    while(isRunning){

        time(&rawtime);

        pTime = localtime(&rawtime);

        printf("\r%02d:%02d:%02d", pTime->tm_hour, pTime->tm_min, pTime->tm_sec);

        if(pTime->tm_hour == 0){
            printf("HAPPY NEW YEAR!!!")
        }

        sleep(1);
    }


    return 0;
}


