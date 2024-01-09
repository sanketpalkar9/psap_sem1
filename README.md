This is project of my first year sem 1 in VIT Pune Computer Engineering

<h1>Color Code Resistance Calculator</h1>

<h2>PSAP - Problem Solving and Programming</h2>
Course Code: ES1034


CODE:

#include <stdio.h>
#include <string.h>

const char *colors[] = {"black", "brown", "red", "orange", "yellow", "green", "blue", "purple", "grey", "white"};

int get_color_value(const char *color) {
  for (int i = 0; i < 10; i++) {
    if (strcmp(colors[i], color) == 0) {
      return i;
    }
  }
  return -1;
}

int main() {
  char color1[10], color2[10], color3[10];
  int resistance;
 
    printf("Hola People!!!");
    printf("\n\t\t Welcome to RESISTENCE CALCULATOR!!!");
    printf("\n\n Let's calculate the resistence of a resistor with four bands.");
    printf("\n Here's a list of the colours used in the resistor colour code to calculate the resistence of a carbon resistor.");
  
  printf("\nBlack\nBrown\nRed\nOrange\nYellow\nGreen\nBlue\nViolet\nGrey\nWhite");
  printf("\nEnter the colours from the above mentioned list.");
  printf("\nEnter the first color: ");
  scanf("%s", color1);
  printf("Enter the second color: ");
  scanf("%s", color2);
  printf("Enter the third color: ");
  scanf("%s", color3);

  int color_value1 = get_color_value(color1);
  int color_value2 = get_color_value(color2);
  int color_value3 = get_color_value(color3);

  if (color_value1 == -1 || color_value2 == -1 || color_value3 == -1) {
    printf("Invalid color entered\n");
    return 0;
  }

  resistance = color_value1 * 10 + color_value2;
  resistance = resistance * (int) pow(10, color_value3);

  printf("The resistance value is: %d ohms\n", resistance);
  return 0;
}
