# Параллелизм и асинхронность

* Замерьте время синхронной проверки ссылок.
* Перепишите код, используя `ThreadPoolExecutor`. 
* Изменяйте количество воркеров: 5, 10, 100.
* Во время работы посмотрите с использованием стандартных утилит вашей OC загрузку памяти, процессора, сети, время работы. Зависят ли они от количества воркеров и как?

  * 5 workers: 96.50568079948425 seconds
  * 10 workers: 25.422240495681763 seconds
  * 100 workers: 18.888001918792725 seconds

Разница составляет 1% между 5 и 100 воркерами. Минимальное значение 0.1%. Максимальное 1.3%   

## CPU-bound. Генерируем монетки

У нас отсутсвует Блокчейн, то есть мы не можем доказать, что монета была сгенерирована именно нами или принадлежит нам: если мы кому-то ее покажем, ее тут же украдут. Эту часть мы оставим за рамками задания.

* Замерьте скорость герации на 1 ядре у вас на компьютере.
* Ускорьтесь за счет использования `ProcessPoolExecutor`.
* Изменяйте количество воркеров: 2, 4, 5, 10, 100.
* Во время работы посмотрите с использованием стандартных утилит вашей OC загрузку памяти, процессора, сети, время работы. Зависят ли они от количества воркеров и как?
* Убедитесь в том, что так как задача CPU bound, наращивать количество воркеров, большее количества ядер, бесполезно.

  * 2 workers: 94.197070837020874 seconds
  * 4 workers: 58.564107233047485 seconds
  * 5 workers: 55.39698505401611 seconds
  * 10 workers: 25.912094116210938 seconds
  * 100 workers: 27.17059063911438 seconds

При увеличении воркеров снижается нагрузка на каждый поток в среднем. Снижается максимальная нагрузка на поток.
