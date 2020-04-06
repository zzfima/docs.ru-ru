---
title: Практическое руководство. Обработка исключений в запросе PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: 5ccddfb01d6b173900dfffc465292c7812626ddc
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80587987"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Практическое руководство. Обработка исключений в запросе PLINQ

В первом примере в этой статье показано, как правильно обрабатывать исключение <xref:System.AggregateException?displayProperty=nameWithType>, создаваемое при выполнении запроса PLINQ. Во втором примере показано, как разместить блоки try-catch в делегатах, то есть максимально близко к точке, в которой будет создано исключение. Этот подход позволит перехватить исключение сразу после создания, и при удачных обстоятельствах продолжить выполнение запроса. Если исключения могут всплывать обратно в присоединяемый поток, запрос может продолжить обработку некоторых элементов после создания исключения.

В некоторых случаях, когда PLINQ прибегает к последовательному выполнению, возникающие исключения могут распространяться напрямую, без оболочки <xref:System.AggregateException>. Кроме того, <xref:System.Threading.ThreadAbortException> всегда распространяются напрямую.

> [!NOTE]
> Если включен режим "Только мой код", Visual Studio прерывает выполнение программы на той строке, в которой создается исключение, и выводит сообщение об ошибке "Exception not handled by user code" (Исключение, не обработанное пользовательским кодом). Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис > Параметры > Отладка > Общие**.
>
> Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. Дополнительные сведения см. в статье [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).

## <a name="example"></a>Пример

В этом примере показано, как поместить блоки try-catch вокруг кода выполнения запроса, чтобы перехватить все создаваемые <xref:System.AggregateException?displayProperty=nameWithType>.

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

Код в этом примере не позволяет обрабатывать запрос после создания исключения. К тому моменту, когда код приложения перехватит исключение, PLINQ уже остановит запрос во всех потоках.

## <a name="example"></a>Пример

В следующем примере показано, как поместить блок try-catch в делегат, чтобы быстро перехватить исключение и продолжить выполнение запроса.

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a>Компиляция кода

- Чтобы скомпилировать и запустить эти примеры, скопируйте их в пример данных для PLINQ и вызовите этот метод из Main.

## <a name="robust-programming"></a>Отказоустойчивость

Не перехватывайте исключение, если не знаете, как его обрабатывать, чтобы не нарушить состояние программы.

## <a name="see-also"></a>См. также раздел

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
