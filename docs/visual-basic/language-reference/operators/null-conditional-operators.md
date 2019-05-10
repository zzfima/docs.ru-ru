---
title: Операторы с условием NULL (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 4815fe7ad337634cfb56127fbd24a47a37fdd74b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65062942"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="4d4d6-102">?.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-102">?.</span></span> <span data-ttu-id="4d4d6-103">и? операторы с условием null () (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d4d6-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="4d4d6-104">Проверяет значение левого операнда со значением NULL (`Nothing`) перед выполнением доступа к членам (`?.`) или индекса (`?()`) операции; возвращает `Nothing` Если левый операнд, результатом которого является `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="4d4d6-105">Обратите внимание, что в выражениях, которые обычно возвращают типы значений, условием null оператор возвращает <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="4d4d6-106">Эти операторы позволяют писать меньше кода для проверок значений null, особенно в том случае, при внедрении в структуры данных.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="4d4d6-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="4d4d6-107">For example:</span></span>

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

<span data-ttu-id="4d4d6-108">Для сравнения является альтернативный код для первого из этих выражений без условного оператора:</span><span class="sxs-lookup"><span data-stu-id="4d4d6-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="4d4d6-109">Иногда требуется выполнить действие на объекте, который может иметь значение null, на основе значения член типа Boolean для этого объекта (значение логического свойства, такие как `IsAllowedFreeShipping` в следующем примере):</span><span class="sxs-lookup"><span data-stu-id="4d4d6-109">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
  Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
  
  If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
   ApplyFreeShippingToOrders(customer)
  End If
```

<span data-ttu-id="4d4d6-110">Можно сократить код и избежать вручную проверки значений NULL с помощью условного оператора, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4d4d6-110">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
 Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
 
 If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="4d4d6-111">Операторы с условием NULL предусматривают сокращенную обработку.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-111">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="4d4d6-112">Если одна операция в цепочке операций доступа и индекс условный член возвращает `Nothing`, остальной части цепочки выполнение останавливается.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-112">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="4d4d6-113">В следующем примере `C(E)` не вычисляется, если `A`, `B`, или `C` принимает значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-113">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="4d4d6-114">Другой член с условием null доступ используется для вызова делегатов в потокобезопасным способом, с гораздо меньшим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-114">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="4d4d6-115">В следующем примере определяется два типа `NewsBroadcaster` и `NewsReceiver`.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-115">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="4d4d6-116">Новости отправляются получателю по `NewsBroadcaster.SendNews` делегировать.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-116">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

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

<span data-ttu-id="4d4d6-117">Если ни один элемент в `SendNews` список вызова, `SendNews` делегат создает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-117">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="4d4d6-118">Перед условные операторы null, код, как следующие гарантируется, что список вызовов делегата не `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="4d4d6-118">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

<span data-ttu-id="4d4d6-119">Новый способ гораздо проще:</span><span class="sxs-lookup"><span data-stu-id="4d4d6-119">The new way is much simpler:</span></span>  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="4d4d6-120">Новый способ является потокобезопасным, так как компилятор создает код для вычисления `SendNews` только один раз, запоминая результат во временной переменной.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-120">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="4d4d6-121">Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `SendNews?(String)` для вызова делегатов с условием NULL.</span><span class="sxs-lookup"><span data-stu-id="4d4d6-121">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4d4d6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4d4d6-122">See also</span></span>

- [<span data-ttu-id="4d4d6-123">Операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d4d6-123">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="4d4d6-124">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d4d6-124">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="4d4d6-125">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d4d6-125">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
