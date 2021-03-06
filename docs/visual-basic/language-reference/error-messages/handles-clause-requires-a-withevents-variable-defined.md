---
title: Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 191415408f607d0ff768e50c41fa9b3c4405a688
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582828"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов

Вы не указали переменную `WithEvents` в предложении `Handles`. Ключевое слово `Handles` в конце объявления процедуры приводит к тому, что оно обрабатывает события, вызванные объектной переменной, объявленной с помощью ключевого слова `WithEvents`.

**Идентификатор ошибки:** BC30506

## <a name="to-correct-this-error"></a>Исправление ошибки

Укажите необходимую переменную `WithEvents`.

## <a name="example"></a>Пример

В следующем примере Visual Basic создает ошибку компилятора `BC30506` поскольку ключевое слово [WithEvents](../modifiers/withevents.md) не используется в определении экземпляра <xref:System.Timers.Timer?displayProperty=nameWithType>.

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

Следующий пример компилируется успешно, так как переменная `_timer1` определена с ключевым словом `WithEvents`:

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a>См. также

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
