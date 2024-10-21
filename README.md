# IHW_1_ACS
ИДЗ №1 по АВС вариант 27
Вариант 11
Условие задачи
Сформировать массив B из элементов A, расположенных в обратном порядке, исключая первый положительный элемент.

Про оформление
Моя работа выполнена на 7 баллов, в своём отчёте я пройдусь по каждому пункту критериев, начиная от 4 баллов до 7 баллов.

Ну что ж, начнём
Критерии на 4 балла:
✅ Приведено решение задачи на C
его можно найти в приложенных файлах
✅ В полученную ассемблерную программу, откомпилированную без оптимизирующих и отладочных опций, добавлены комментарии, поясняющие эквивалентное представление переменных в программе на C.
код на ассемблере и его комментирование можно найти в файлах с расширением .s
✅ Из ассемблерной программы убраны лишние макросы за счет использования соответствующих аргументов командной строки и/или за счет ручного редактирования исходного текста ассемблерной программы.
Программа откомпилирована при помощи флагов gcc

gcc -masm=intel
-fno-asynchronous-unwind-tables
-fno-jump-tables
-fno-stack-protector
-fno-exceptions
./code.c
-S -o ./code.s

✅ Модифицированная ассемблерная программа отдельно откомпилирована и скомпонована без использования опций отладки.
имеются исполняемые файлы
✅ Представлено полное тестовое покрытие, дающее одинаковый результат на обоих программах. Приведены результаты тестовых прогонов для обоих программ, демонстрирующие эквивалентность функционирования.
про тесты будет сказано ниже (они есть)
Критерии на 5 баллов:
✅ В реализованной программе использовать функции с передачей данных через параметры.
в программе есть вызов функций, каждая из которых принимает 1 и более параметров
✅ Использовать локальные переменные.
каждая функция использует локальные перменные
некоторые из них (ориентируясь на код си) max_size main.c, index в new_array и т.д
✅ В ассемблерную программу при вызове функции добавить комментарии, описывающие передачу фактических параметров и перенос возвращаемого результата.
при вызове функций в коде ассемблера в скобках указано, в каких регистрах лежат передаваемые занчения
также даны комментарии, в каком регистре лежит какое возвращаемое значение
✅ В функциях для формальных параметров добавить комментарии, описывающие связь между параметрами языка Си и регистрами (стеком)
Критерии на 6 баллов:
✅ Рефакторинг программы на ассемблере за счет максимального использования регистров процессора. Добавление этой программы к уже представленным.
во всех функциях переменная i (счётчик цикла) заменена регистром r12d (на стеке была по адресу -4[rbp])
в main.s переменная max_size(отвечает за максимально возможный размер массива, на стеке была по адресу -8[rbp]) заменена регистром r13d
в new_array.s и в write_array.s index(позиция 1-ого положительного элемента) заменена на r14d (до этого находилась на стеке по адресу -20[rbp])
в new_array.s переменная flag из стека по адресу -16[rbp] перемещена в регистр r13d Важное уточнение: если я в другой функции использую тот же регистр, что и в прошлой, то старое значение затирается (если я так делаю, то оно больше мне не потребуется) Всё, что идёт далее в пункте на 6 баллов выполнено
Критерии на 7 баллов:
✅ Реализация программы на ассемблере, полученной после рефакторинга, в виде двух или более единиц компиляции.
моя программа реализована в виде 3 единиц компиляции
файлы main.s, new_array.s, write_array.s (лежат в репозитории)
✅ Задание файлов с исходными данными и файла для вывода результатов с использованием аргументов командной строки.
программа считывает элементы массива из файла
результат нового массива В печатается в файл
имя входного и выходного файлов передаются через аргументы командной строки Далее тоже выполнено
