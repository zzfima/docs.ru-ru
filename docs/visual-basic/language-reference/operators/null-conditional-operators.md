---
title: Операторы с условием NULL (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: b83435b8448b53eca63aac0519e9eed2f7dfa9f3
ms.sourcegitcommit: 344d82456f27d09a210671214a14cfd7daf1f97c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58348769"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="07321-102">?.</span><span class="sxs-lookup"><span data-stu-id="07321-102">?.</span></span> <span data-ttu-id="07321-103">и? операторы с условием null () (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07321-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="07321-104">Проверяет значение левого операнда со значением NULL (`Nothing`) перед выполнением доступа к членам (`?.`) или индекса (`?()`) операции; возвращает `Nothing` Если левый операнд, результатом которого является `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="07321-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="07321-105">Обратите внимание, что в выражениях, которые обычно возвращают типы значений, условием null оператор возвращает <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="07321-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="07321-106">Эти операторы позволяют писать меньше кода для проверок значений null, особенно в том случае, при внедрении в структуры данных.</span><span class="sxs-lookup"><span data-stu-id="07321-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="07321-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="07321-107">For example:</span></span>

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

<span data-ttu-id="07321-108">Для сравнения является альтернативный код для первого из этих выражений без условного оператора:</span><span class="sxs-lookup"><span data-stu-id="07321-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="07321-109">Операторы с условием NULL предусматривают сокращенную обработку.</span><span class="sxs-lookup"><span data-stu-id="07321-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="07321-110">Если одна операция в цепочке операций доступа и индекс условный член возвращает `Nothing`, остальной части цепочки выполнение останавливается.</span><span class="sxs-lookup"><span data-stu-id="07321-110">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="07321-111">В следующем примере `C(E)` не вычисляется, если `A`, `B`, или `C` принимает значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="07321-111">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="07321-112">Другой член с условием null доступ используется для вызова делегатов в потокобезопасным способом, с гораздо меньшим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="07321-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="07321-113">В следующем примере определяется два типа `NewsBroadcaster` и `NewsReceiver`.</span><span class="sxs-lookup"><span data-stu-id="07321-113">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="07321-114">Новости отправляются получателю по `NewsBroadcaster.SendNews` делегировать.</span><span class="sxs-lookup"><span data-stu-id="07321-114">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String) 

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

<span data-ttu-id="07321-115">Если ни один элемент в `SendNews` список вызова, `SendNews` делегат создает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="07321-115">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="07321-116">Перед условные операторы null, код, как следующие гарантируется, что список вызовов делегата не `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="07321-116">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

<span data-ttu-id="07321-117">Новый способ гораздо проще:</span><span class="sxs-lookup"><span data-stu-id="07321-117">The new way is much simpler:</span></span>  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="07321-118">Новый способ является потокобезопасным, так как компилятор создает код для вычисления `SendNews` только один раз, запоминая результат во временной переменной.</span><span class="sxs-lookup"><span data-stu-id="07321-118">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="07321-119">Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `SendNews?(String)` для вызова делегатов с условием NULL.</span><span class="sxs-lookup"><span data-stu-id="07321-119">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="07321-120">См. также</span><span class="sxs-lookup"><span data-stu-id="07321-120">See also</span></span>

- [<span data-ttu-id="07321-121">Операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07321-121">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="07321-122">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07321-122">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="07321-123">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07321-123">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
