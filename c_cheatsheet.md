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