---
title: Parallel LINQ (PLINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
ms.openlocfilehash: 1ea880c6403a5fc8b26ba67fe21dfce79c4683db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140036"
---
# <a name="parallel-linq-plinq"></a>Parallel LINQ (PLINQ)
Parallel LINQ (PLINQ) является параллельной реализацией LINQ to Objects. PLINQ реализует полный набор стандартных операторов запроса LINQ как методов расширения для пространства имен <xref:System.Linq> и имеет дополнительные операторы для параллельных операций. PLINQ объединяет простоту и удобство чтения синтаксиса LINQ с мощностью параллельного программирования. Подобно коду, предназначенному для библиотеки параллельных задач, запросы PLINQ масштабируются в степень параллелизма на основе возможностей главного компьютера.  
  
 Во многих сценариях PLINQ может значительно увеличить скорость запросов LINQ to Objects, более эффективно используя все доступные ядра на главном компьютере. Повышенная производительность увеличивает мощность высокопроизводительных вычислений на настольных компьютерах.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Введение в PLINQ](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [Сохранение порядка в PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [Параметры слияния в PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [Практическое руководство. Создание и выполнение простого запроса PLINQ](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [Практическое руководство. Управление порядком в запросе PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [Практическое руководство. Объединение параллельных и последовательных запросов LINQ](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [Практическое руководство. Обработка исключений в запросе PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [Практическое руководство. Отмена запроса PLINQ](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [Практическое руководство. Написание пользовательской агрегатной функции PLINQ](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [Практическое руководство. Задание режима выполнения в PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [Практическое руководство. Задание параметров слияния в PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [Практическое руководство. Перебор каталогов с файлами с помощью PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [Практическое руководство. Измерение производительности запросов PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [Пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq.ParallelEnumerable>
- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
- [LINQ — C#](../../csharp/programming-guide/concepts/linq/index.md)  
- [LINQ — Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md)  
