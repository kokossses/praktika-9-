#include <stdio.h>
#include <math.h>
int min_steps(int x, int y) {
    int distance = y - x;
    int step_length = 1;
    int steps = 0;
    int total_distance_covered = 0;
    while (total_distance_covered < distance) {
        steps++;
        total_distance_covered += step_length;
        if (total_distance_covered >= distance) break;
        steps++;
        total_distance_covered += step_length;
        step_length++;
    }
    return steps;
}
int main() {
    int x, y;
    printf("Enter the values of x and y: ");
    scanf("%d %d", &x, &y);
    if (x < 0 || y < 0 || x > y || y >= 2147483648) {
        printf("Invalid input\n");
        return 1;
    }
    int result = min_steps(x, y);
    printf("Minimum steps: %d\n", result);
    return 0;
}
