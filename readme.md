# Ввід-вивід
Бібліотека:
```c
#include <stdio.h>
```

## Консоль
Ввід-вивід одного символу:
```c
char c;
c = getchar(); //ввід
putchar(c); //вивід
```

Ввід-вивід строки:
```c
char str[255];
gets(str); //ввід
puts(str); //вивід
```

Форматований ввід-вивід:
[scanf](https://cplusplus.com/reference/cstdio/scanf/)
[printf](https://cplusplus.com/reference/cstdio/printf/)

## Робота з файлами
Зчитування:
```c
FILE *fp;
char buff[255];

fp = fopen("input.txt", "r");
fscanf(fp, "%s", buff);
fclose(fp);
```
Зчитати весь файл:
```c
FILE *fp;

int buff_len = 255;
char buff[buff_len];
fp = fopen("input.txt", "r");
while(fgets(buff, buff_len, fp)) {
    printf("%s\n", buff);
}
fclose(fp);
```
Запис:
```c
FILE *fp;

fp = fopen("output.txt", "w");
fprintf(fp, "This is testing for fprintf...\n");
fclose(fp);
```
[c file I/O](https://www.tutorialspoint.com/cprogramming/c_file_io.htm)

# Строки
Бібліотека:
```c
#include <string.h>
```

Довжина строки:
```c
char a[255] = "Program";
int len = strlen(a);
//len = 7
```

Підстрока:
```c
char substr[255];
strncpy(substr, buff+10, 4); // 4 символа починаючи з позиції 10
```

Конкатенація:
```c
char str[255];
strcpy(str, "Hello ");
strcat(str, "world!");
//str = "Hello world!"
```

# Динамічні масиви
## Одновимірний
```c
#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
...

int n;
scanf("%d", &n);
int *a = (int*)malloc(n * sizeof(int));

int i;
for (i = 0; i < n; i++) {
    scanf("%d", &a[i]);
}

for (i = 0; i < n; i++) {
    printf("%d ", a[i]);
}

free(a);
```

## Двовимірний
```c
#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
...

int n, m;
scanf("%d %d", &n, &m);
int** a = (int**)malloc(n * sizeof(int*));
for (int i = 0; i < n; i++) {
    a[i] = (int*)malloc(m * sizeof(int));
}

int i, j;
for (i = 0; i < n; i++) {
    for (j = 0; j < m; j++) {
        scanf("%d", &a[i][j]);
    }
}

for (i = 0; i < n; i++) {
    for (j = 0; j < m; j++) {
        printf("%d ", a[i][j]);
    }
    printf("\n");
}

for (i = 0; i < n; i++) {
    free(a[i]);
}
free(a);
```
