---
title: Пространства имен (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 0e678f6577c07e4d56c485e0fd104397eddbd079
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517459"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="bcf6e-102">Пространства имен (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="bcf6e-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="bcf6e-103">Пространства имен часто используются в программировании на C# двумя способами.</span><span class="sxs-lookup"><span data-stu-id="bcf6e-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="bcf6e-104">Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bcf6e-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="bcf6e-105">`System` является пространством имен, а `Console` — это класс в нем.</span><span class="sxs-lookup"><span data-stu-id="bcf6e-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="bcf6e-106">Можно использовать ключевое слово `using`, и тогда полное имя не потребуется. См. следующий пример:</span><span class="sxs-lookup"><span data-stu-id="bcf6e-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 <span data-ttu-id="bcf6e-107">Подробнее см. разделе [Директива using](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="bcf6e-107">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="bcf6e-108">Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах.</span><span class="sxs-lookup"><span data-stu-id="bcf6e-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="bcf6e-109">Используйте ключевое слово [namespace](../../../csharp/language-reference/keywords/namespace.md), чтобы объявить пространство имен, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bcf6e-109">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a><span data-ttu-id="bcf6e-110">Обзор пространств имен</span><span class="sxs-lookup"><span data-stu-id="bcf6e-110">Namespaces Overview</span></span>  
 <span data-ttu-id="bcf6e-111">Пространства имен имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="bcf6e-111">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="bcf6e-112">Они помогают упорядочивать проекты с большим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="bcf6e-112">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="bcf6e-113">Они разделяются оператором `.`.</span><span class="sxs-lookup"><span data-stu-id="bcf6e-113">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="bcf6e-114">`using directive` позволяет не указывать название пространства имен для каждого класса.</span><span class="sxs-lookup"><span data-stu-id="bcf6e-114">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="bcf6e-115">Пространство имен `global` является "корневым": `global::System` всегда будет ссылаться на пространство имен `System` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bcf6e-115">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bcf6e-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bcf6e-116">Related Sections</span></span>  
 <span data-ttu-id="bcf6e-117">Дополнительные сведения о пространствах имен см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bcf6e-117">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="bcf6e-118">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="bcf6e-118">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="bcf6e-119">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="bcf6e-119">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="bcf6e-120">Практическое руководство. Использование пространства имен My</span><span class="sxs-lookup"><span data-stu-id="bcf6e-120">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="bcf6e-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bcf6e-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bcf6e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="bcf6e-122">See Also</span></span>

- [<span data-ttu-id="bcf6e-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bcf6e-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bcf6e-124">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="bcf6e-124">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="bcf6e-125">Директива using</span><span class="sxs-lookup"><span data-stu-id="bcf6e-125">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
- [<span data-ttu-id="bcf6e-126">Оператор ::</span><span class="sxs-lookup"><span data-stu-id="bcf6e-126">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="bcf6e-127">. Оператор</span><span class="sxs-lookup"><span data-stu-id="bcf6e-127">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
