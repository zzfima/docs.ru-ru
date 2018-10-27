---
title: Операторы с условием NULL (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: c29362a1e335e18b66821919e266b1ce57774692
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195999"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="629fb-102">?.</span><span class="sxs-lookup"><span data-stu-id="629fb-102">?.</span></span> <span data-ttu-id="629fb-103">и? операторы с условием null () (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="629fb-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="629fb-104">Проверяет значение левого операнда со значением NULL (`Nothing`) перед выполнением доступа к членам (`?.`) или индекса (`?()`) операции; возвращает `Nothing` Если левый операнд, результатом которого является `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="629fb-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="629fb-105">Обратите внимание, что, в выражениях, которые обычно возвращает типы значений, условием null оператор возвращает <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="629fb-105">Note that, in the expressions that would ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="629fb-106">Эти операторы позволяют писать меньше кода для проверок значений null, особенно в том случае, при внедрении в структуры данных.</span><span class="sxs-lookup"><span data-stu-id="629fb-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="629fb-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="629fb-107">For example:</span></span>

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

<span data-ttu-id="629fb-108">Для сравнения является альтернативный код для первого из этих выражений без условного оператора:</span><span class="sxs-lookup"><span data-stu-id="629fb-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="629fb-109">Операторы с условием NULL предусматривают сокращенную обработку.</span><span class="sxs-lookup"><span data-stu-id="629fb-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="629fb-110">Если одна операция в цепочке операций доступа и индекс условный член возвращает значение Nothing, остальной части цепочки останавливается.</span><span class="sxs-lookup"><span data-stu-id="629fb-110">If one operation in a chain of conditional member access and index operations returns Nothing, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="629fb-111">В следующем примере, если не вычисляется C(E) `A`, `B`, или `C` бесполезным.</span><span class="sxs-lookup"><span data-stu-id="629fb-111">In the following example, C(E) isn't evaluated if `A`, `B`, or `C` evaluates to Nothing.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="629fb-112">Другой член с условием null доступ используется для вызова делегатов в потокобезопасным способом, с гораздо меньшим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="629fb-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="629fb-113">Для старого способа требуется примерно следующий код:</span><span class="sxs-lookup"><span data-stu-id="629fb-113">The old way requires code like the following:</span></span>  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

<span data-ttu-id="629fb-114">Новый способ гораздо проще:</span><span class="sxs-lookup"><span data-stu-id="629fb-114">The new way is much simpler:</span></span>  

```vb
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="629fb-115">Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной.</span><span class="sxs-lookup"><span data-stu-id="629fb-115">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="629fb-116">Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.</span><span class="sxs-lookup"><span data-stu-id="629fb-116">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="629fb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="629fb-117">See also</span></span>

- [<span data-ttu-id="629fb-118">Операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="629fb-118">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="629fb-119">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="629fb-119">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="629fb-120">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="629fb-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
