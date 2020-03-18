---
title: Практическое руководство. Использование метода Parallel.Invoke для выполнения параллельных операций
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 665490601cad9ccd7881042aed576b95bbc07115
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139730"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Практическое руководство. Использование метода Parallel.Invoke для выполнения параллельных операций

В этом примере показывается, как параллелизовать операции с помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> в библиотеке параллельных задач. В общем источнике данных выполняются три операции. Поскольку ни одна из этих операций не изменяет источник, они могут выполняться параллельно простым способом.

> [!NOTE]
> В этой документации для определения делегатов в библиотеке параллельных задач используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Пример

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

Обратите внимание, что с помощью метода <xref:System.Threading.Tasks.Parallel.Invoke%2A> можно просто указать, какие действия должны выполняться параллельно, и среда выполнения обработает все сведения по планированию потока, включая автоматическое масштабирование на число ядер в главном компьютере.

В этом примере параллелизуются операции, но не данные. Как вариант можно параллелизовать запросы LINQ с помощью PLINQ и выполнять эти запросы последовательно. Кроме того, можно параллелизовать данные с помощью PLINQ. Другим вариантом является параллелизация запросов и задач. Хотя итоговая нагрузка может снизить производительность главных компьютеров с относительно небольшим числом процессоров, масштабирование будет выполняться гораздо лучше на компьютерах с большим числом процессоров.

## <a name="compile-the-code"></a>Компиляция кода

Скопируйте и вставьте весь пример в проект Microsoft Visual Studio и нажмите клавишу **F5**.

## <a name="see-also"></a>См. также раздел

- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
- [Практическое руководство. Отмена задачи и ее дочерних элементов](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
