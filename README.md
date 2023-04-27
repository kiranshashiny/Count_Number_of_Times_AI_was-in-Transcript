# Count_Number_of_Times_AI_was-in-Transcript


This C program reads an input file and counts the number of times the word "AI" appears in it.




```
// C program to implement
// the above approach
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Driver code
int main(int argc , char *argv[])
{
	FILE* ptr;
	char filename[30];

	int count=0;
  	int ai_count=0;
	char ch;

	if ( argc == 1 ) {
		printf ("Please enter the name of the transcript to read from \n");
		return 1;
	}

	strcpy ( filename , argv[1] );
	ptr = fopen(filename, "r");

	if (NULL == ptr) {
		printf("file can't be opened \n");
	}

	printf("content of this file are \n");

	while (!feof(ptr)) {
		ch = fgetc(ptr);
		printf("[%d %c]", count, ch);
		if ( ch == 'A' ) {
			// do something.
			printf ( "Found A\n");
			ch = fgetc ( ptr );
			count++;
			if ( ch == 'I' ) { 
					printf("[%d %c]", count, ch);
					printf ( "Found I");
					ai_count++;
			} else {
					printf("[%d %c]", count, ch);

			}
		}

		count++;
		
		printf ("\n");
	}
	fclose(ptr);
	count=count-1;
	printf("Number of characters = %d\n ",count );
	printf("AI was printed %d times",ai_count); 
	printf ("\n\n\n");
	return 0;
}

```


