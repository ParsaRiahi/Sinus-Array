# Sinus-Array
2 files called sin.c and sin2.c

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <math.h>


void printArray (float array[], int size)
{
    int j;
    for(j = 0; j < size; j = j + 1)
    {
        printf("at %d array is %f \n", j, array[j]);    
    }
}

int main(void)
{
    int size;
    int i;
    float *array;
    const float pi = 3.1415926535;

    printf("\nenter the size of the array\n");
    scanf("%d",&size);

    array = malloc(sizeof(int) * size);

    srand(time(0));

    for(i = 0; i < size; i = i + 1)
    {
        array[i] = sin(i * 2 * M_PI / size);
    }

    printArray(array, size);
    free(array);

    return 0;
}

////////////////////////////////////////////////////////////////////////////////////

#include <stdio.h>
#include <time.h>
#include <math.h>
#include <stdlib.h>

void sinfunc(float *array, int size)
{
    const float pi = M_PI;
    float increment = (2 * pi) / size;

    for(int i = 0; i < size; i = i + 1)
    {
        float angle = i * increment;
        array[i] = sin(angle);
    }
}

int main(void)
{   
    int size;
    const float pi = M_PI;
    
    srand(time(NULL));

    printf("Enter an array size:\n");
    scanf("%d", &size);

    float array[size];
    int i;

    printf("\n");

    sinfunc(array, size);

    printf("array after sin function:\n");

    for(i = 0; i < size; i = i + 1)
    {
        printf("%.5f ", array[i]);
    }
    printf("\n");
    
    return 0;
}
