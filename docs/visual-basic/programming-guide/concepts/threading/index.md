---
title: "Работа с потоками (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b544d63651b481ec39f7e07d4e7f549923d2a475
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="threading-visual-basic"></a>Работа с потоками (Visual Basic)
Потоки позволяют программе на Visual Basic осуществлять параллельную обработку, то есть вы можете выполнять несколько операций одновременно. Например, потоки можно использовать для отслеживания пользовательского ввода, выполнения фоновых задач и одновременной обработки нескольких потоков ввода.  
  
 Потоки имеют следующие свойства.  
  
-   Потоки позволяют программе выполнять параллельную обработку.  
  
-   Пространство имен <xref:System.Threading> платформы .NET Framework упрощает использование потоков.  
  
-   Потоки используют одни и те же ресурсы приложения. Дополнительные сведения см. в разделе [Использование потоков и работа с потоками](../../../../standard/threading/using-threads-and-threading.md).  
  
 По умолчанию программа на Visual Basic имеет один поток. Но можно также создавать вспомогательные потоки и выполнять в них код параллельно основному. Эти потоки часто называются *рабочими потоками*.  
  
 Рабочие потоки можно использовать для выполнения трудоемких или срочных задач без прерывания основного потока. Рабочие потоки часто используются, например, в серверных приложениях, когда необходимо обработать входящий запрос, не дожидаясь завершения обработки предыдущего запроса. Кроме того, они используются для выполнения «фоновых» задач в настольных приложениях, что позволяет не занимать ресурсы основного потока, ответственного за работу пользовательского интерфейса.  
  
 Применение потоков позволяет решить проблемы с пропускной способностью и быстротой работы системы, но оно также может привести к проблемам с совместным использованием ресурсов, например к конфликтам и взаимоблокировкам. Использование нескольких потоков лучше всего подходит в тех случаях, когда разные задачи используют разные ресурсы, например дескрипторы файлов и сетевые подключения. Назначение нескольких потоков одному ресурсу, вероятнее всего, вызовет проблемы синхронизации и частую блокировку из-за ожидания, что сделает само использование нескольких потоков нецелесообразным.  
  
 Обычно рабочие потоки используются для выполнения трудоемких или срочных задач, которым не требуется большое количество ресурсов, занятых другими потоками. Естественно, некоторые используемые программой ресурсы должны быть доступны нескольким потокам. Для таких случаев в пространстве имен <xref:System.Threading> доступны классы по синхронизации потоков. К таким классам относятся <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> и <xref:System.Threading.ManualResetEvent>.  
  
 Вы можете использовать все классы или некоторые из них для синхронизации работы нескольких потоков, но некоторые функции для потоков поддерживаются также и языком Visual Basic. Например [оператор SyncLock](../../../../visual-basic/language-reference/statements/synclock-statement.md) дает возможность синхронизации за счет неявного использования класса <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], многопоточное программирование значительно упростилось благодаря классам <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), новым классам параллельной коллекции из пространства имен <xref:System.Collections.Concurrent?displayProperty=nameWithType> и новой модели программирования, которая вместо потоков использует концепцию задач. Дополнительные сведения см. в разделе [Параллельное программирование](../../../../standard/parallel-programming/index.md).  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание:|  
|-----------|-----------------|  
|[Многопоточные приложения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)|Описание создания и использования потоков.|  
|[Параметры и возвращаемые значения для многопоточных процедур (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|Описание передачи и возвращения параметров в многопоточных приложениях.|  
|[Пошаговое руководство. Многопоточность с помощью компонента BackgroundWorker (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|Пример создания простого многопоточного приложения.|  
|[Синхронизация потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)|Описание управления взаимодействием потоков.|  
|[Таймеры потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md)|Описание запуска процедур в отдельных потоках через фиксированные промежутки времени.|  
|[Группировка потоков в пул (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)|Описание использования пула рабочих потоков, управляемых системой.|  
|[Практическое руководство. Использование пула потоков (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|Демонстрация синхронизированного использования нескольких потоков в пуле.|  
|[Работа с потоками](../../../../standard/threading/index.md)|Описание реализации работы с потоками на платформе .NET Framework.|
