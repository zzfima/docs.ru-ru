---
title: private (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 89bc23e91bf693f0a95b75dffe2399cb7e865b50
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171867"
---
# <a name="private-c-reference"></a><span data-ttu-id="156da-102">private (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="156da-102">private (C# Reference)</span></span>
<span data-ttu-id="156da-103">Ключевое слово `private` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="156da-103">The `private` keyword is a member access modifier.</span></span> 
   
 > <span data-ttu-id="156da-104">Эта страница содержит доступ `private`.</span><span class="sxs-lookup"><span data-stu-id="156da-104">This page covers `private` access.</span></span> <span data-ttu-id="156da-105">Ключевое слово `private` также является частью модификатора доступа [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="156da-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>
  
<span data-ttu-id="156da-106">Закрытый доступ является уровнем доступа с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="156da-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="156da-107">Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="156da-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```csharp  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 <span data-ttu-id="156da-108">Вложенные типы в том же теле могут также обращаться к таким закрытым членам.</span><span class="sxs-lookup"><span data-stu-id="156da-108">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="156da-109">Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.</span><span class="sxs-lookup"><span data-stu-id="156da-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="156da-110">Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="156da-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="156da-111">Пример</span><span class="sxs-lookup"><span data-stu-id="156da-111">Example</span></span>  
 <span data-ttu-id="156da-112">В этом примере класс `Employee` содержит два закрытых элемента данных — `name` и `salary`.</span><span class="sxs-lookup"><span data-stu-id="156da-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="156da-113">Как к закрытым членам, к ним нельзя получить доступ, кроме как через методы членов.</span><span class="sxs-lookup"><span data-stu-id="156da-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="156da-114">Для получения управляемого доступа к закрытым членам можно использовать открытые методы `GetName` и `Salary`.</span><span class="sxs-lookup"><span data-stu-id="156da-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="156da-115">Доступ к члену `name` можно поучить через открытый метод, а к члену `salary` — через открытое свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="156da-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="156da-116">(Дополнительные сведения см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="156da-116">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="156da-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="156da-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="156da-118">См. также</span><span class="sxs-lookup"><span data-stu-id="156da-118">See Also</span></span>  
 [<span data-ttu-id="156da-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="156da-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="156da-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="156da-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="156da-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="156da-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="156da-122">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="156da-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="156da-123">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="156da-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="156da-124">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="156da-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="156da-125">public</span><span class="sxs-lookup"><span data-stu-id="156da-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="156da-126">protected</span><span class="sxs-lookup"><span data-stu-id="156da-126">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="156da-127">internal</span><span class="sxs-lookup"><span data-stu-id="156da-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
