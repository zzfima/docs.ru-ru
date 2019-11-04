---
title: Практическое руководство. Отмена запроса PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: 272f25d62cb63c60209be3bc54dc5e76fb30df54
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134228"
---
# <a name="how-to-cancel-a-plinq-query"></a>Практическое руководство. Отмена запроса PLINQ
В приведенных ниже примерах показаны два способа отмены запроса PLINQ. В первом примере отменяется запрос, который состоит в основном из обхода данных. Во втором примере отменяется запрос, который содержит ресурсоемкую функцию.

> [!NOTE]
> Если включен режим "Только мой код", Visual Studio прерывает выполнение программы на той строке, в которой создается исключение, и выводит сообщение об ошибке "Exception not handled by user code" (Исключение, не обработанное пользовательским кодом). Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис > Параметры > Отладка > Общие**.
>
> Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. См. дополнительные сведения об [ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).

## <a name="example"></a>Пример

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

Платформа PLINQ не помещает единственное <xref:System.OperationCanceledException> в <xref:System.AggregateException?displayProperty=nameWithType>. <xref:System.OperationCanceledException> нужно обрабатывать в отдельном блоке catch. Если один или несколько пользовательских делегатов создают исключение OperationCanceledException(externalCT) (с помощью внешнего объекта <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), но не создают других исключений, и при этом запрос был определен как `AsParallel().WithCancellation(externalCT)`, то PLINQ выдает одно исключение <xref:System.OperationCanceledException> (externalCT), но не <xref:System.AggregateException?displayProperty=nameWithType>. Тем не менее, если один пользовательский делегат создает исключение <xref:System.OperationCanceledException>, а другой делегат создает исключение другого типа, то оба этих исключения помещаются в <xref:System.AggregateException>.

Общие рекомендации по отмене:

1. Если вы отменяете пользовательский делегат, известите PLINQ о внешнем <xref:System.Threading.CancellationToken> и создайте исключение <xref:System.OperationCanceledException>(externalCT).

2. Если выполняется только отмена и нет других исключений, обрабатывайте <xref:System.OperationCanceledException>, а не <xref:System.AggregateException>.

## <a name="example"></a>Пример

В следующем примере показано, как правильно обрабатывать отмену пользовательского кода, который содержит ресурсоемкую функцию.

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

Если вы обрабатываете отмену в пользовательском коде, нет необходимости использовать <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> в определении запроса. Но мы все же рекомендуем это сделать, ведь <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> не влияет на производительность запросов, но зато позволяет обрабатывать отмену как в операторах запроса, так и в пользовательском коде.

Чтобы обеспечить высокую скорость реагирования системы, мы рекомендуем проверять отмену приблизительно каждую миллисекунду. Впрочем, здесь считается допустимым любой период вплоть до 10 мс. Частота проверок должна быть такой, чтобы не снижать производительность кода.

Если удаляется перечислитель, например когда код прерывается вне цикла foreach (For Each в Visual Basic), выполняющего итерацию по результатам запроса, то этот запрос отменяется без создания исключений.

## <a name="see-also"></a>См. также

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
- [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
