---
title: "Пространства имен (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
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
ms.openlocfilehash: a45339a4c3320a92c0339b1cad6345a2555ed920
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="3880b-102">Пространства имен (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="3880b-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="3880b-103">Пространства имен часто используются в программировании на C# двумя способами.</span><span class="sxs-lookup"><span data-stu-id="3880b-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="3880b-104">Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3880b-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 <span data-ttu-id="3880b-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3880b-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="3880b-106">`System` является пространством имен, а `Console` — это класс в нем.</span><span class="sxs-lookup"><span data-stu-id="3880b-106">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="3880b-107">Можно использовать ключевое слово `using`, и тогда полное имя не потребуется. См. следующий пример:</span><span class="sxs-lookup"><span data-stu-id="3880b-107">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 <span data-ttu-id="3880b-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3880b-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span></span>  
  
 <span data-ttu-id="3880b-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3880b-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span></span>  
  
 <span data-ttu-id="3880b-110">Подробнее см. разделе [Директива using](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="3880b-110">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="3880b-111">Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах.</span><span class="sxs-lookup"><span data-stu-id="3880b-111">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="3880b-112">Используйте ключевое слово [namespace](../../../csharp/language-reference/keywords/namespace.md), чтобы объявить пространство имен, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3880b-112">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 <span data-ttu-id="3880b-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3880b-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span></span>  
  
## <a name="namespaces-overview"></a><span data-ttu-id="3880b-114">Обзор пространств имен</span><span class="sxs-lookup"><span data-stu-id="3880b-114">Namespaces Overview</span></span>  
 <span data-ttu-id="3880b-115">Пространства имен имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="3880b-115">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="3880b-116">Они помогают упорядочивать проекты с большим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="3880b-116">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="3880b-117">Они разделяются оператором `.`.</span><span class="sxs-lookup"><span data-stu-id="3880b-117">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="3880b-118">`using directive` позволяет не указывать название пространства имен для каждого класса.</span><span class="sxs-lookup"><span data-stu-id="3880b-118">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="3880b-119">Пространство имен `global` является "корневым": `global::System` всегда будет ссылаться на пространство имен `System` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3880b-119">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3880b-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3880b-120">Related Sections</span></span>  
 <span data-ttu-id="3880b-121">Дополнительные сведения о пространствах имен см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3880b-121">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="3880b-122">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="3880b-122">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="3880b-123">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="3880b-123">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="3880b-124">Практическое руководство. Использование пространства имен My</span><span class="sxs-lookup"><span data-stu-id="3880b-124">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="3880b-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3880b-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3880b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3880b-126">See Also</span></span>  
 <span data-ttu-id="3880b-127">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3880b-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3880b-128">[Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="3880b-128">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="3880b-129">[Директива using](../../../csharp/language-reference/keywords/using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="3880b-129">[using Directive](../../../csharp/language-reference/keywords/using-directive.md) </span></span>  
 <span data-ttu-id="3880b-130">[Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="3880b-130">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="3880b-131">. Оператор</span><span class="sxs-lookup"><span data-stu-id="3880b-131">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)

