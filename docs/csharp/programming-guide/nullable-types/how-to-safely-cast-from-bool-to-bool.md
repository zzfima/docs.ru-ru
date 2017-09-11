---
title: "Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c8a3dc3280b7dca802b327d9454c7f0ba9ed44be
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="12bdd-102">Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="12bdd-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="12bdd-103">Тип `bool?`, допускающий значение NULL, может содержать три разных значения: `true`, `false` и `null`.</span><span class="sxs-lookup"><span data-stu-id="12bdd-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="12bdd-104">Следовательно, тип `bool?` невозможно использовать в условных операторах, например с `if`, `for` или `while`.</span><span class="sxs-lookup"><span data-stu-id="12bdd-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="12bdd-105">Так, следующий код вызовет ошибку компиляции.</span><span class="sxs-lookup"><span data-stu-id="12bdd-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="12bdd-106">Это запрещено, так как непонятно, что означает `null` в контексте условного оператора.</span><span class="sxs-lookup"><span data-stu-id="12bdd-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="12bdd-107">Чтобы использовать `bool?` в условном операторе, сначала проверьте свойство <xref:System.Nullable%601.HasValue%2A>, чтобы убедиться, что его значение не равно `null`, а затем приведите его к типу `bool`.</span><span class="sxs-lookup"><span data-stu-id="12bdd-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="12bdd-108">Дополнительные сведения: [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="12bdd-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="12bdd-109">Если вы выполняете приведение для `bool?` со значением `null`, проверка условия создает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="12bdd-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="12bdd-110">В следующем примере показан один из способов безопасного приведения из `bool?` к `bool`:</span><span class="sxs-lookup"><span data-stu-id="12bdd-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="12bdd-111">Пример</span><span class="sxs-lookup"><span data-stu-id="12bdd-111">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12bdd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="12bdd-112">See Also</span></span>  
 <span data-ttu-id="12bdd-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="12bdd-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="12bdd-114">[Буквенные ключевые слова](../../../csharp/language-reference/keywords/literal-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="12bdd-114">[Literal Keywords](../../../csharp/language-reference/keywords/literal-keywords.md) </span></span>  
 <span data-ttu-id="12bdd-115">[Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="12bdd-115">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="12bdd-116">?? Оператор</span><span class="sxs-lookup"><span data-stu-id="12bdd-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

