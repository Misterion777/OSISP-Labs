# Lab4
Создать дерево процессов согласно следующей последовательности: 

(5 вар) 1 -> (2, 3, 4, 5) 5 -> (6, 7, 8) 

Организовать непрерывный обмен сигналами согласно следующей последовательности:

(9 вар) 1->2 SIGUSR2   2->(3,4,5) SIGUSR1   4->6 SIGUSR1   
        3->7 SIGUSR1  5->8 SIGUSR1 8->1 SIGUSR2 

Процесс 1, после получения  101 –го по счету сигнала SIGUSR,  посылает сыновьям сигнал SIGTERM и ожидает  завершения всех сыновей, после чего завершается сам. 

Сыновья, получив сигнал SIGTERM, завершают работу с выводом на консоль сообщения вида:
pid ppid завершил работу после X-го сигнала SIGUSR1 и Y-го сигнала SIGUSR2,
где X,Y – количество посланных за все время работы данным сыном сигналов SIGUSR1 и SIGUSR2
