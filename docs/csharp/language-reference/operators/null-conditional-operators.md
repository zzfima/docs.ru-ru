---
title: Операторы проверки на NULL (Справочник по C#)
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 823b9dc886bf2448ca9da4ac640bfe56f90d3ff3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194856"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="9d68c-102">?.</span><span class="sxs-lookup"><span data-stu-id="9d68c-102">?.</span></span> <span data-ttu-id="9d68c-103">и ?[]: операторы с условием NULL (C# и Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d68c-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="9d68c-104">Проверяет значение левого операнда на наличие значения NULL перед выполнением операции доступа к элементу (`?.`) или индексу (`?[]`). Возвращает `null`, если левый операнд имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="9d68c-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span> 

<span data-ttu-id="9d68c-105">Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.</span><span class="sxs-lookup"><span data-stu-id="9d68c-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="9d68c-106">Операторы с условием NULL предусматривают сокращенную обработку.</span><span class="sxs-lookup"><span data-stu-id="9d68c-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="9d68c-107">Если одна из операций в цепочке условных операций доступа к члену и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки прекращается.</span><span class="sxs-lookup"><span data-stu-id="9d68c-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="9d68c-108">В приведенном ниже примере `E` не выполняется, если `A`, `B` или `C` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9d68c-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

 <span data-ttu-id="9d68c-109">Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="9d68c-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="9d68c-110">Для старого способа требуется примерно следующий код:</span><span class="sxs-lookup"><span data-stu-id="9d68c-110">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
  
 <span data-ttu-id="9d68c-111">Новый способ гораздо проще:</span><span class="sxs-lookup"><span data-stu-id="9d68c-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

 <span data-ttu-id="9d68c-112">Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной.</span><span class="sxs-lookup"><span data-stu-id="9d68c-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="9d68c-113">Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.</span><span class="sxs-lookup"><span data-stu-id="9d68c-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="9d68c-114">Спецификации языков</span><span class="sxs-lookup"><span data-stu-id="9d68c-114">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9d68c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9d68c-115">See Also</span></span>

- [<span data-ttu-id="9d68c-116">Оператор ?? (оператор объединения со значением NULL)</span><span class="sxs-lookup"><span data-stu-id="9d68c-116">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)  
- [<span data-ttu-id="9d68c-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9d68c-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9d68c-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9d68c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
