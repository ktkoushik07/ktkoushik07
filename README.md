#include <stdio.h>

typedef struct {
    char *name;
    char *location;
    char *degree;
    char *university;
    float cgpa;
    char *stack[6];
    char *learning[3];
    char *funFact;
} Developer;

Developer koushik = {
    .name       = "Koushik KT",
    .location   = "Chennai, Tamil Nadu, India 🇮🇳",
    .degree     = "B.E. – Electronics & Communication Engg.",
    .university = "R.M.D. Engineering College, Anna University",
    .cgpa       = 8.35,
    .stack      = {
        "C", "C++", "Python",
        "Arduino IDE", "KiCad", "Tinkercad"
    },
    .learning   = {
        "VLSI Design",
        "IoT Systems",
        "PCB Design"
    },
    .funFact    = "I debug circuits before code 🔌"
};

void motto() {
    printf("Build. Break. Learn. Repeat.\n");
}