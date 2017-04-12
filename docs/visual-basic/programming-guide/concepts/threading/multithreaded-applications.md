---
title: "Многопоточные приложения (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5bde7f49a2f2bc8a2e6c1eeab3722428b8a37a95
ms.lasthandoff: 03/13/2017

---
# <a name="multithreaded-applications-visual-basic"></a>Многопоточные приложения (Visual Basic)
С помощью Visual Basic можно писать приложения, которые выполняют несколько задач одновременно. Задачи, которые могут задержать выполнение других задач могут выполнять в отдельных потоках, этот процесс называется *многопоточность* или *освобождения потоков*.  
  
 Приложения, использующие многопоточность, более реагирования на действия пользователя, поскольку пользовательский интерфейс остается активным, как процессор задачи выполняются в других потоках. Многопотоковость также полезна при создании масштабируемых приложений, поскольку пользователь может добавлять потоки при увеличении рабочей нагрузки.  
  
## <a name="creating-and-using-threads"></a>Создание и использование потоков  
 Если требуется больший контроль над поведением потоков приложения, можно управлять потоками самостоятельно. Однако учтите, что написание правильных многопоточных приложений может быть трудно: приложение может перестать отвечать на запросы или взаимодействия временных ошибок, вызванных конкуренции. Дополнительные сведения см. в разделе [потокобезопасные компоненты](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).  
  
 Новый поток создается путем объявления переменной типа <xref:System.Threading.Thread>и вызова конструктора, которому предоставляется имя процедуры или метода, необходимо выполнить в новом потоке.</xref:System.Threading.Thread> Ниже приведен пример кода.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>Запуск и остановка потоков  
 Чтобы начать выполнение нового потока, используйте <xref:System.Threading.Thread.Start%2A>метод, как показано в следующем коде.</xref:System.Threading.Thread.Start%2A>  
  
```vb  
newThread.Start()  
```  
  
 Чтобы остановить выполнение потока, используйте <xref:System.Threading.Thread.Abort%2A>метод, как показано в следующем коде.</xref:System.Threading.Thread.Abort%2A>  
  
```vb  
newThread.Abort()  
```  
  
 Помимо запуска и остановки потоков, можно приостанавливать потоки, вызывая <xref:System.Threading.Thread.Sleep%2A>или <xref:System.Threading.Thread.Suspend%2A>метод, возобновление приостановленного потока с помощью <xref:System.Threading.Thread.Resume%2A>метода и уничтожать поток с помощью <xref:System.Threading.Thread.Abort%2A>метода</xref:System.Threading.Thread.Abort%2A> </xref:System.Threading.Thread.Resume%2A> </xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Sleep%2A>  
  
### <a name="thread-methods"></a>Методы управления потоками  
 Ниже приведены некоторые методы, которые можно использовать для управления отдельными потоками.  
  
|Метод|Действие|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>|Вынуждает поток начнут выполняться.|  
|<xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>|Приостанавливает поток на заданное время.|  
|<xref:System.Threading.Thread.Suspend%2A></xref:System.Threading.Thread.Suspend%2A>|Приостанавливает поток, когда он достигает безопасной точки.|  
|<xref:System.Threading.Thread.Abort%2A></xref:System.Threading.Thread.Abort%2A>|Останавливает поток, когда он достигает безопасной точки.|  
|<xref:System.Threading.Thread.Resume%2A></xref:System.Threading.Thread.Resume%2A>|Перезапускает приостановленного потока|  
|<xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>|Вызывает текущий поток для ожидания завершения другого потока. Если используется значение времени ожидания, метод возвращает `True` Если поток завершается в назначенное время.|  
  
### <a name="safe-points"></a>Безопасные точки  
 Большинство этих методов говорят сами за себя, но понятие *точках, безопасных* может оказаться новой для пользователя. Безопасные точки располагаются в местах кода, в которых может безопасно для среды CLR для выполнения автоматического *мусора*, процесс уничтожения неиспользуемых переменных и освобождения памяти. При вызове <xref:System.Threading.Thread.Abort%2A>или <xref:System.Threading.Thread.Suspend%2A>метод потока, общеязыковая среда выполнения анализирует код и определяет подходящее место для остановки потока.</xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Abort%2A>  
  
### <a name="thread-properties"></a>Свойства потока  
 Потоки также имеют несколько полезных свойств, как показано в следующей таблице.  
  
|Свойство|Значение|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A></xref:System.Threading.Thread.IsAlive%2A>|Содержит значение `True` , если поток активен.|  
|<xref:System.Threading.Thread.IsBackground%2A></xref:System.Threading.Thread.IsBackground%2A>|Возвращает или задает логическое значение, указывающее, если поток или должно быть в фоновом потоке. Фоновые потоки отличаются от основного потока, но в фоновом потоке не запрещает процесс остановки. Когда будут остановлены все основные потоки, принадлежащие процессу, общеязыковая среда выполнения завершает процесс путем вызова <xref:System.Threading.Thread.Abort%2A>метод в фоновых потоках, которые еще продолжают существовать.</xref:System.Threading.Thread.Abort%2A>|  
|<xref:System.Threading.Thread.Name%2A></xref:System.Threading.Thread.Name%2A>|Возвращает или задает имя потока. Чаще всего используется для обнаружения отдельных потоков при отладке.|  
|<xref:System.Threading.Thread.Priority%2A></xref:System.Threading.Thread.Priority%2A>|Возвращает или задает значение, которое используется операционной системой для установки приоритетов потоков.|  
|<xref:System.Threading.Thread.ThreadState%2A></xref:System.Threading.Thread.ThreadState%2A>|Содержит значение, описывающее состояние или состояния потока.|  
  
## <a name="thread-priorities"></a>Приоритеты потоков  
 Каждый поток имеет приоритетное свойство, которое определяет от размера фрагмента процессорного времени, ей нужно выполнить. Операционная система выделяет более длинные отрезки времени на потоки с высоким приоритетом и более короткие отрезки времени потоки с низким приоритетом. Новые потоки создаются со значением `Normal`, но можно изменить <xref:System.Threading.Thread.Priority%2A>любое значение в свойства <xref:System.Threading.ThreadPriority>перечисления.</xref:System.Threading.ThreadPriority> </xref:System.Threading.Thread.Priority%2A>  
  
 В разделе <xref:System.Threading.ThreadPriority>Подробное описание различных приоритетов потоков.</xref:System.Threading.ThreadPriority>  
  
## <a name="foreground-and-background-threads"></a>Основные и фоновые потоки  
 Объект *основной поток* выполняется бесконечно, тогда как *фоновый поток* останавливается сразу после остановки последнего основного потока. Можно использовать <xref:System.Threading.Thread.IsBackground%2A>Свойства для определения или изменения фонового статуса потока.</xref:System.Threading.Thread.IsBackground%2A>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 [Синхронизация потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)   
 [Параметры и возвращаемые значения для многопоточных процедур (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)   
 [Работа с потоками (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
