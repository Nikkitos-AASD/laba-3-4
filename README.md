# laba-3-4

вариант - Объявление целочисленной константы с инициализацией на языке Kotlinв

В данной работе рассматриваются объявление целочисленной константы с инициализацией на языке Kotlin. В общем виде объявление констант выглядят так:
const val number: int = 10 ;
Где “number” – это название переменной, а целочисленное число – число из диапазона от -2147483648 до 2147483647.

2 Разработка грамматики
G[Z]
P:
1)<START> -> 'const' <SPACE_AFTER_FINAL>
2)<SPACE_AFTER_FINAL> -> ' ' <TYPE>
3)<TYPE> -> 'val' <SPACE_AFTER_TYPE>
4)<SPACE_AFTER_TYPE> -> ' ' <VAR>
5)<VAR> -> indicator_symb <VARREM>
6)<VARREM> -> symb <VARREM>
7) <VARREM> - > ‘:’ <INT>
8)<INT> -> ‘int’ <EQUAL>
9)<EQUAL> -> ‘=’ <NUM>
10)<NUMBER> -> "+" < NUMBER >
11)<NUMBER> -> "-" < NUMBER >
12)<NUMBER> -> digit <INTREM>
13)<INTREM> -> digit <INTREM>
14)<INTREM> -> ';'
-----------------------------------------------------------------------------------------
digit -> 1|...|0
indicator_symb -> a|...|z|A|...|Z|'_' 
symb -> a|...|z|A|...|Z|'_'|1|...|9
Vn = {<START>, <SPACE_AFTER_FINAL>, <SPACE_AFTER_TYPE>, <TYPE>, <VAR>, <VARREM>, <NUMBER>, <INTREM>}
Vt = {a|...|z|A|...|Z|'_'|1|...|9, ' ', 'int', '+', '-', 'final', digit, symb, indicator_symb}  
3 Классификация грамматики

Представленная выше грамматика описывает правила порождения строк с помощью праворекурсивных продукций. Согласно классификации Хомского, грамматика является автоматной (регулярной):
•	<START> -> 'const' <SPACE_AFTER_FINAL>
•	<SPACE_AFTER_FINAL> -> ' ' <TYPE>
•	<TYPE> -> 'val' <SPACE_AFTER_TYPE>
•	<SPACE_AFTER_TYPE> -> ' ' <VAR>
•	<VAR> -> indicator_symb <VARREM>
•	<NUMBER> -> '+' <INTREM>
•	<NUMBER> -> '-' <INTREM>
•	<NUMBER> -> digit <INTREM>
•	<INTREM> -> digit <INTREM>
•	<VARREM> -> symb <VARREM>
•	<VARREM> -> ':' <VARREM>
•	<VARREM> -> 'int' <VARREM>
•	<VARREM> -> '=' <NUMBER>






4 Метод анализа
Грамматика G[Z] является автоматной.
Правила (1) – (11) для G[Z] реализованы на графе (см. рисунок 1).
Сплошные стрелки на графе характеризуют синтаксически верный разбор; пунктирные символизируют состояние ошибки (ERROR); дуга λ и непомеченные дуги предполагают любой терминальный символ, отличный от указанного из соответствующего узла. 
 ![image](https://github.com/user-attachments/assets/421b0e9c-db59-4fc2-8fe4-d97a7c8622c1)

Рисунок  – Граф G[Z]

5. тестовые примеры
![image](https://github.com/user-attachments/assets/eeee8374-9129-4d53-98d6-31503b09f7a3)
![image](https://github.com/user-attachments/assets/d6cd7947-7098-46e3-a9fa-9789737ee76d)
![image](https://github.com/user-attachments/assets/6497fbce-d56e-4be9-b7d9-426e4054de28)



