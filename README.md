# №1

### Per base sequence content
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Pbsc%2073_1.png)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Pbsc%2073_2.png)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Pbsc%20old.png)

Можем наблюдать, что графики выглядят по-разному:
В первом случае (SRR5836473_1) почти отсутствует Цитозин (C), по крайней мере его гораздо меньше чем в РНК, в отличие от Тимина (T) – его содержание, наоборот, больше, чем в РНК, cодержание Гуанина (G) и Ацетозин (А) же примерно на равном уровне, по сравнению с РНК (SRR3414630_1).

## Per sequence GC content
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/PbGCc%2073_1.png)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/PbGCc%2073_2.png)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/PbGCc%20old.png)

Видим, что на первом графике наблюдается (теоретически) нормальное распределение, однако немного смещенное.

# №2

# hse_hw1_meth
[Colab](https://colab.research.google.com/drive/1adEVel6P7qKHvHKsaQzHZFRMijNlUubr?usp=sharing)

##(a), (b) Таблица с числм ридов, закартированных на участках 11347700-11367700; 40185800-40195800 и процентом дуплицированных прочтений для каждого образца

### Число ридов
BS-Seq | ch11: 11347700-11367700 | ch11: 40185800-40195800 | deduplication 
--- | --- | --- | ---
SRR5836473 | 1090 | 464 | 81.69
SRR3824222 | 2328 | 1062 | 97.08
SRR5836475 | 1456 | 630 | 90.92

## bash
```
!ls *pe.bam | xargs -P 4 -tI{} deduplicate_bismark  --bam  --paired  -o s_{} {}
```

##(d) M-bias plots

На графиках изображена уровень метилирования каждой возможной позиции в прочтении. На графиках по оси Y слева видно значение Methylation calls, справа -- пропорцию метилирования. Так как у нас парно-концевая запись, то для каждого запуска представлено 2 разных графика.

### SRR3824222
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Bismark_M-bias%20Read_1_22.png)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Bismark_M-bias%20Read_2_22.png) 

### SRR5836473
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Bismark_M-bias%20Read_1_73.png)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Bismark_M-bias%20Read_2_73.png) 

### SRR5836475
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Bismark_M-bias%20Read_1_75.png)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Bismark_M-bias%20Read_2_75.png) 

## (e) Гистограмы распределения метелирования цитозинов по хромосоме
### SRR3824222 (Epiblast)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/Epiblast.png)
### SRR5836473 (8 Cell)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/8cell.png)
### SRR5836475 (ICM)
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/ICM.png)

Можно сделать вывод, что для каждого образца частота и процент метилляции зависят по-разному. Для первого образца чаще всего метилируется 0%, почти в 40 процентов случаев. Для второго образца чаще всего 100%, что достаточно хороший показатель, так как метилирование принимает участие в экспрессии гена. В третьем образце чаще всего (почти в 60% случаев) метилируется 0% цитозинов.

## (f) Визуализация уровеня метилирования и покрытия для каждого образца
### Уровень метилирования
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/plot_1.png)
### Уровень покрытия
![Image](https://github.com/Vladm0z/hse_hw1_meth/blob/main/data/plot_2.png)

