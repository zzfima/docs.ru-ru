---
title: private (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9cc8f86166888b47a758e200182d319c68ca6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="private-c-reference"></a><span data-ttu-id="1b953-102">private (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1b953-102">private (C# Reference)</span></span>
<span data-ttu-id="1b953-103">Ключевое слово `private` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="1b953-103">The `private` keyword is a member access modifier.</span></span> 
   
 > <span data-ttu-id="1b953-104">Эта страница содержит `private` доступа.</span><span class="sxs-lookup"><span data-stu-id="1b953-104">This page covers `private` access.</span></span> <span data-ttu-id="1b953-105">`private` Также ключевое слово является частью [ `private protected` ](./private-protected.md) модификатор доступа.</span><span class="sxs-lookup"><span data-stu-id="1b953-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>
  
<span data-ttu-id="1b953-106">Закрытый доступ является уровнем доступа с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="1b953-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="1b953-107">Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1b953-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 <span data-ttu-id="1b953-108">Вложенные типы в том же теле могут также обращаться к таким закрытым членам.</span><span class="sxs-lookup"><span data-stu-id="1b953-108">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="1b953-109">Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.</span><span class="sxs-lookup"><span data-stu-id="1b953-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="1b953-110">Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="1b953-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b953-111">Пример</span><span class="sxs-lookup"><span data-stu-id="1b953-111">Example</span></span>  
 <span data-ttu-id="1b953-112">В этом примере класс `Employee` содержит два закрытых элемента данных — `name` и `salary`.</span><span class="sxs-lookup"><span data-stu-id="1b953-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="1b953-113">Как к закрытым членам, к ним нельзя получить доступ, кроме как через методы членов.</span><span class="sxs-lookup"><span data-stu-id="1b953-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="1b953-114">Для получения управляемого доступа к закрытым членам можно использовать открытые методы `GetName` и `Salary`.</span><span class="sxs-lookup"><span data-stu-id="1b953-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="1b953-115">Доступ к члену `name` можно поучить через открытый метод, а к члену `salary` — через открытое свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1b953-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="1b953-116">(Дополнительные сведения см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="1b953-116">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="1b953-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1b953-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b953-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1b953-118">See Also</span></span>  
 [<span data-ttu-id="1b953-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1b953-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1b953-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1b953-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1b953-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="1b953-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1b953-122">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="1b953-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="1b953-123">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="1b953-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="1b953-124">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="1b953-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="1b953-125">public</span><span class="sxs-lookup"><span data-stu-id="1b953-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="1b953-126">protected</span><span class="sxs-lookup"><span data-stu-id="1b953-126">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="1b953-127">internal</span><span class="sxs-lookup"><span data-stu-id="1b953-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
