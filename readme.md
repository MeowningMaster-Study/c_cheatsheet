# Ввод-вывод
Библиотека:
```c
#include <stdio.h>
```

## Консоль
Ввод-вывод одного символа:
```c
char c;
c = getchar(); //ввод
putchar(c); //вывод
```

Ввод-вывод строки:
```c
char str[255];
gets(str); //ввод
puts(str); //вывод
```

Форматированый ввод-вывод:
[scanf](https://metanit.com/cpp/c/2.14.php)
[printf](https://metanit.com/cpp/c/2.4.php)

## Работа с файлами
Считывание:
```c
FILE *fp;
char buff[255];

fp = fopen("input.txt", "r");
fscanf(fp, "%s", buff);
fclose(fp);
```
Считать весь файл:
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
Запись:
```c
FILE *fp;

fp = fopen("output.txt", "w");
fprintf(fp, "This is testing for fprintf...\n");
fclose(fp);
```
Больше инфы тут: [c file I/O](https://www.tutorialspoint.com/cprogramming/c_file_io.htm)

# Строки
Библиотека:
```c
#include <string.h>
```

Длина строки:
```c
char a[255] = "Program";
int len = strlen(a);
//len = 7
```

Подстрока:
```c
char substr[255];
strncpy(substr, buff+10, 4); //4 символа начиная с позиции 10
```

Склеивание:
```c
char str[255];
strcpy(str, "Hello ");
strcat(str, "world!");
//str = "Hello world!"
```

# Динамические массивы
## Одномерный
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

## Двумерный
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
