---
title: Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 04c94d3d32660d1a186a9bb377c49a53e1451be6
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512731"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="aa831-102">Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов</span><span class="sxs-lookup"><span data-stu-id="aa831-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>
<span data-ttu-id="aa831-103">Вы не указали `WithEvents` переменную `Handles` в предложении.</span><span class="sxs-lookup"><span data-stu-id="aa831-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="aa831-104">Ключевое слово в конце объявления процедуры вызывает обработку событий, вызванных переменной объекта, объявленной `WithEvents` с помощью ключевого слова. `Handles`</span><span class="sxs-lookup"><span data-stu-id="aa831-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>
  
 <span data-ttu-id="aa831-105">**Идентификатор ошибки:** BC30506</span><span class="sxs-lookup"><span data-stu-id="aa831-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="aa831-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="aa831-106">To correct this error</span></span>
  
- <span data-ttu-id="aa831-107">Укажите необходимую `WithEvents` переменную.</span><span class="sxs-lookup"><span data-stu-id="aa831-107">Supply the necessary `WithEvents` variable.</span></span>
  
## <a name="example"></a><span data-ttu-id="aa831-108">Пример</span><span class="sxs-lookup"><span data-stu-id="aa831-108">Example</span></span>

<span data-ttu-id="aa831-109">В следующем примере Visual Basic создает ошибку `BC30506` компилятора, так как ключевое слово [WithEvents](../modifiers/withevents.md) не используется в определении <xref:System.Timers.Timer?displayProperty=nameWithType> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="aa831-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="aa831-110">Следующий пример компилируется успешно, так как `_timer1` переменная определена `WithEvents` с помощью ключевого слова:</span><span class="sxs-lookup"><span data-stu-id="aa831-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="aa831-111">См. также</span><span class="sxs-lookup"><span data-stu-id="aa831-111">See also</span></span>

- [<span data-ttu-id="aa831-112">Handles</span><span class="sxs-lookup"><span data-stu-id="aa831-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
