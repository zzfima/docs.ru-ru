---
title: "Практическое руководство. Переопределение метода ToString (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
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
ms.openlocfilehash: 60cec855286a3bb572a0bacd08c0f7920a1fc912
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="6f7d3-102">Практическое руководство. Переопределение метода ToString (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6f7d3-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="6f7d3-103">Каждый класс или структура в языке C# неявно наследует класс <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="6f7d3-104">Поэтому каждый объект в языке C# получает метод <xref:System.Object.ToString%2A>, который возвращает строковое представление данного объекта.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="6f7d3-105">Например, все переменные типа `int` имеют метод `ToString`, который позволяет им возвращать их содержимое в виде строки:</span><span class="sxs-lookup"><span data-stu-id="6f7d3-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 <span data-ttu-id="6f7d3-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6f7d3-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span></span>  
  
 <span data-ttu-id="6f7d3-107">При создании пользовательского класса или структуры необходимо переопределить метод <xref:System.Object.ToString%2A>, чтобы передать информацию о типе клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-107">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="6f7d3-108">Дополнительные сведения об использовании строк форматирования и других типов пользовательского форматирования с методом `ToString` см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="6f7d3-108">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f7d3-109">При принятии решения относительно того, какая информация должна будет предоставляться посредством этого метода, подумайте, будет ли создаваемый класс или структура когда-либо использоваться ненадежным кодом.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-109">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="6f7d3-110">Постарайтесь не предоставлять информацию, которая может быть использована вредоносным кодом.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-110">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="6f7d3-111">Переопределение метода ToString в классе или структуре</span><span class="sxs-lookup"><span data-stu-id="6f7d3-111">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="6f7d3-112">Объявите метод `ToString` со следующими модификаторами и типом возвращаемого значения:</span><span class="sxs-lookup"><span data-stu-id="6f7d3-112">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="6f7d3-113">Реализуйте этот метод таким образом, чтобы он возвращал строку.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-113">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="6f7d3-114">В приведенном ниже примере возвращается не только имя класса, но и специфические данные для конкретного экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-114">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     <span data-ttu-id="6f7d3-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6f7d3-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span></span>  
  
     <span data-ttu-id="6f7d3-116">Метод `ToString` можно проверить с помощью показанного ниже кода.</span><span class="sxs-lookup"><span data-stu-id="6f7d3-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     <span data-ttu-id="6f7d3-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6f7d3-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7d3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6f7d3-118">See Also</span></span>  
 <span data-ttu-id="6f7d3-119"><xref:System.IFormattable></span><span class="sxs-lookup"><span data-stu-id="6f7d3-119"><xref:System.IFormattable></span></span>   
 <span data-ttu-id="6f7d3-120">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6f7d3-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6f7d3-121">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="6f7d3-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="6f7d3-122">[Строки](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="6f7d3-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="6f7d3-123">[string](../../../csharp/language-reference/keywords/string.md) </span><span class="sxs-lookup"><span data-stu-id="6f7d3-123">[string](../../../csharp/language-reference/keywords/string.md) </span></span>  
 <span data-ttu-id="6f7d3-124">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="6f7d3-124">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 <span data-ttu-id="6f7d3-125">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="6f7d3-125">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 <span data-ttu-id="6f7d3-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="6f7d3-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 [<span data-ttu-id="6f7d3-127">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="6f7d3-127">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

