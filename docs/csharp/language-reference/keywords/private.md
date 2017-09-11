---
title: "private (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- private_CSharpKeyword
- private
dev_langs:
- CSharp
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
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
ms.openlocfilehash: c18fd87b12bf3f7f1a1d1ef0dfded8643308169c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="private-c-reference"></a><span data-ttu-id="e75e9-102">private (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e75e9-102">private (C# Reference)</span></span>
<span data-ttu-id="e75e9-103">Ключевое слово `private` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="e75e9-103">The `private` keyword is a member access modifier.</span></span> <span data-ttu-id="e75e9-104">Закрытый доступ является уровнем доступа с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="e75e9-104">Private access is the least permissive access level.</span></span> <span data-ttu-id="e75e9-105">Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e75e9-105">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 <span data-ttu-id="e75e9-106">Вложенные типы в том же теле могут также обращаться к таким закрытым членам.</span><span class="sxs-lookup"><span data-stu-id="e75e9-106">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="e75e9-107">Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.</span><span class="sxs-lookup"><span data-stu-id="e75e9-107">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="e75e9-108">Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="e75e9-108">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e75e9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e75e9-109">Example</span></span>  
 <span data-ttu-id="e75e9-110">В этом примере класс `Employee` содержит два закрытых элемента данных — `name` и `salary`.</span><span class="sxs-lookup"><span data-stu-id="e75e9-110">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="e75e9-111">Как к закрытым членам, к ним нельзя получить доступ, кроме как через методы членов.</span><span class="sxs-lookup"><span data-stu-id="e75e9-111">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="e75e9-112">Для получения управляемого доступа к закрытым членам можно использовать открытые методы `GetName` и `Salary`.</span><span class="sxs-lookup"><span data-stu-id="e75e9-112">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="e75e9-113">Доступ к члену `name` можно поучить через открытый метод, а к члену `salary` — через открытое свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e75e9-113">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="e75e9-114">(Дополнительные сведения см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="e75e9-114">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 <span data-ttu-id="e75e9-115">[!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e75e9-115">[!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e75e9-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e75e9-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e75e9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e75e9-117">See Also</span></span>  
 <span data-ttu-id="e75e9-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e75e9-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e75e9-120">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e75e9-121">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="e75e9-122">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="e75e9-123">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="e75e9-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="e75e9-125">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="e75e9-125">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="e75e9-126">internal</span><span class="sxs-lookup"><span data-stu-id="e75e9-126">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

