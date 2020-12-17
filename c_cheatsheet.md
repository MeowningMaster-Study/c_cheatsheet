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
char str[50];
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

fp = fopen("/tmp/test.txt", "r");
fscanf(fp, "%s", buff);
fgets(buff, 255, (FILE*)fp);
fgets(buff, 255, (FILE*)fp);
fclose(fp);
```
Запись:
```c
FILE *fp;

fp = fopen("/tmp/test.txt", "w+");
fprintf(fp, "This is testing for fprintf...\n");
fputs("This is testing for fputs...\n", fp);
fclose(fp);
```
Больше инфы тут: [c file input/output](https://www.tutorialspoint.com/cprogramming/c_file_io.htm)