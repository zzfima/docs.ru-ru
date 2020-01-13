---
title: Практическое руководство. Переопределение метода ToString (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 7c7196df56821c134b31982d7956a75039e9f929
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705578"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="d6c32-102">Практическое руководство. Переопределение метода ToString (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d6c32-102">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="d6c32-103">Каждый класс или структура в языке C# неявно наследует класс <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="d6c32-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="d6c32-104">Поэтому каждый объект в языке C# получает метод <xref:System.Object.ToString%2A>, который возвращает строковое представление данного объекта.</span><span class="sxs-lookup"><span data-stu-id="d6c32-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="d6c32-105">Например, все переменные типа `int` имеют метод `ToString`, который позволяет им возвращать их содержимое в виде строки:</span><span class="sxs-lookup"><span data-stu-id="d6c32-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="d6c32-106">При создании пользовательского класса или структуры необходимо переопределить метод <xref:System.Object.ToString%2A>, чтобы передать информацию о типе клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="d6c32-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="d6c32-107">Дополнительные сведения об использовании строк форматирования и других типов пользовательского форматирования с методом `ToString` см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="d6c32-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d6c32-108">При принятии решения относительно того, какая информация должна будет предоставляться посредством этого метода, подумайте, будет ли создаваемый класс или структура когда-либо использоваться ненадежным кодом.</span><span class="sxs-lookup"><span data-stu-id="d6c32-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="d6c32-109">Постарайтесь не предоставлять информацию, которая может быть использована вредоносным кодом.</span><span class="sxs-lookup"><span data-stu-id="d6c32-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="d6c32-110">Чтобы переопределить метод `ToString` в классе или структуре, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d6c32-110">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="d6c32-111">Объявите метод `ToString` со следующими модификаторами и типом возвращаемого значения:</span><span class="sxs-lookup"><span data-stu-id="d6c32-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="d6c32-112">Реализуйте этот метод таким образом, чтобы он возвращал строку.</span><span class="sxs-lookup"><span data-stu-id="d6c32-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="d6c32-113">В приведенном ниже примере возвращается не только имя класса, но и специфические данные для конкретного экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="d6c32-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="d6c32-114">Метод `ToString` можно проверить с помощью показанного ниже кода.</span><span class="sxs-lookup"><span data-stu-id="d6c32-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="d6c32-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d6c32-115">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="d6c32-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d6c32-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d6c32-117">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="d6c32-117">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="d6c32-118">Строки</span><span class="sxs-lookup"><span data-stu-id="d6c32-118">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="d6c32-119">string</span><span class="sxs-lookup"><span data-stu-id="d6c32-119">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="d6c32-120">override</span><span class="sxs-lookup"><span data-stu-id="d6c32-120">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="d6c32-121">virtual</span><span class="sxs-lookup"><span data-stu-id="d6c32-121">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="d6c32-122">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="d6c32-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
