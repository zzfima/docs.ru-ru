---
title: Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
ms.openlocfilehash: e04e34abd477730f9dd01486ec6bddcde4943edc
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457506"
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="7ac73-102">Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7ac73-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="7ac73-103">Тип `bool?`, допускающий значение NULL, может содержать три разных значения: `true`, `false` и `null`.</span><span class="sxs-lookup"><span data-stu-id="7ac73-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="7ac73-104">Следовательно, тип `bool?` невозможно использовать в условных операторах, например с `if`, `for` или `while`.</span><span class="sxs-lookup"><span data-stu-id="7ac73-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="7ac73-105">Так, следующий код вызовет ошибку компиляции.</span><span class="sxs-lookup"><span data-stu-id="7ac73-105">For example, the following code causes a compiler error.</span></span>  
  
```csharp  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="7ac73-106">Это запрещено, так как непонятно, что означает `null` в контексте условного оператора.</span><span class="sxs-lookup"><span data-stu-id="7ac73-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="7ac73-107">Чтобы использовать `bool?` в условном операторе, сначала проверьте свойство <xref:System.Nullable%601.HasValue%2A>, чтобы убедиться, что его значение не равно `null`, а затем приведите его к типу `bool`.</span><span class="sxs-lookup"><span data-stu-id="7ac73-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="7ac73-108">Дополнительные сведения: [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="7ac73-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="7ac73-109">Если вы выполняете приведение для `bool?` со значением `null`, проверка условия создает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="7ac73-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="7ac73-110">В следующем примере показан один из способов безопасного приведения из `bool?` к `bool`:</span><span class="sxs-lookup"><span data-stu-id="7ac73-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ac73-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7ac73-111">Example</span></span>  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ac73-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7ac73-112">See Also</span></span>  
 [<span data-ttu-id="7ac73-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7ac73-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7ac73-114">Буквенные ключевые слова</span><span class="sxs-lookup"><span data-stu-id="7ac73-114">Literal Keywords</span></span>](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [<span data-ttu-id="7ac73-115">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="7ac73-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="7ac73-116">?? Оператор</span><span class="sxs-lookup"><span data-stu-id="7ac73-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
