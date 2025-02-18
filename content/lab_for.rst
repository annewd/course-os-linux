Цикл for
########

:date: 2021-05-10
:summary: Описание лабы
:author: Бекбаева И.В.

.. contents:: Содержание

Теоретическая часть
=====================

Вы уже познакомились с циклом while. С помощью него можно обеспечить выполнение команд списка до тех пор, пока условие не станет ложным. Если же требуется выполнить команду строго определенное число раз, удобно использовать цикл for:

for var in список_значений

do список

done

Оператор for обеспечивает выполнение цикла столько раз, сколько слов в списке значений. При этом переменная var последовательно принимает значения, равные словам из списка. Список может формироваться различными способами, например, как вывод некоторой команды (`имя_команды_формирующей_список`).

Создайте скрипт с данным кодом и запустите его.

.. code-block:: bash

  #!/bin/bash
  for i in `seq 0 9`
  do
        echo $i
  done

Каков будет вывод после запуска скрипта? Проверьте себя, создав скрипт с данным кодом и запустив его.

.. code-block:: bash

  #!/bin/bash
  for i in `seq 1 10`
  do
       echo $i*$i = $((i*i))
  done

В данных примерах команда `seq start step stop` генерирует арифметическую последовательность и соответствует функции range в python. Однако в качестве списка значений можно использовать не только числа, например, следующий скрипт выведет список файлов, содержащихся в текущей директории:

.. code-block:: bash

  #!/bin/bash
  for i in `ls`
  do
        echo $i
  done

Функция ls после выполнения вернет список файлов в текущей директории, а переменная i примет последовательно значения каждого элемента данного списка.

Что произойдет при запуске данных скриптов? Проверьте себя, запустив код.

.. code-block:: bash

  #!/bin/bash
  a='Mary will eat only things starting with "a". What will eat Mary? She can choose from apples, bananas, ananas, milk, meat, oranges, yogurt, cheese, avocado.'
  echo $a
  for i in $a
  do
        case $i in
                a*)
                        echo -n "$i "

                        ;;
        esac
  done
  echo "Great job!"

.. code-block:: bash

   #!/bin/bash
   read n

   for i in `seq 0 1 $n`
   do
     	echo "This is the file number $i." > file$i.txt
   done

Практическая часть
===================

Задачи
-------------

Подсчет голосов
~~~~~~~~~~~~~~~~~~~~~
3 кандидата баллотируются на пост мэра города. Данные о голосовании собираются в виде строки '1 1 3 3 2 3 2', где цифра обозначает голос за соответствующего кандидата. Требуется написать скрипт, который поможет определить, кто набрал больше голосов.

Сумма чисел
~~~~~~~~~~~~
Напишите скрипт, который находит сумму чисел в строке

Функция grep
~~~~~~~~~~~~~
Вводится предложение и фильтр. Требуется с помощью цикла for отфильтровать предложение по заданному фильтру. (Написать функцию grep, используя цикл for)

Калькулятор
~~~~~~~~~~~~~
Реализуйте простой калькулятор, который считывает числа и операнды ("+", "-") и выполняет вычисления.
