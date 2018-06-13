---
title: Пространства имен (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 60e4c6e98ca9e71d1a095a0c7ee1df6be6d13f4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334354"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="905ef-102">Пространства имен (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="905ef-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="905ef-103">Пространства имен часто используются в программировании на C# двумя способами.</span><span class="sxs-lookup"><span data-stu-id="905ef-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="905ef-104">Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="905ef-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="905ef-105">`System` является пространством имен, а `Console` — это класс в нем.</span><span class="sxs-lookup"><span data-stu-id="905ef-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="905ef-106">Можно использовать ключевое слово `using`, и тогда полное имя не потребуется. См. следующий пример:</span><span class="sxs-lookup"><span data-stu-id="905ef-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 <span data-ttu-id="905ef-107">Подробнее см. разделе [Директива using](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="905ef-107">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="905ef-108">Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах.</span><span class="sxs-lookup"><span data-stu-id="905ef-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="905ef-109">Используйте ключевое слово [namespace](../../../csharp/language-reference/keywords/namespace.md), чтобы объявить пространство имен, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="905ef-109">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a><span data-ttu-id="905ef-110">Обзор пространств имен</span><span class="sxs-lookup"><span data-stu-id="905ef-110">Namespaces Overview</span></span>  
 <span data-ttu-id="905ef-111">Пространства имен имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="905ef-111">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="905ef-112">Они помогают упорядочивать проекты с большим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="905ef-112">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="905ef-113">Они разделяются оператором `.`.</span><span class="sxs-lookup"><span data-stu-id="905ef-113">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="905ef-114">`using directive` позволяет не указывать название пространства имен для каждого класса.</span><span class="sxs-lookup"><span data-stu-id="905ef-114">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="905ef-115">Пространство имен `global` является "корневым": `global::System` всегда будет ссылаться на пространство имен `System` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="905ef-115">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="905ef-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="905ef-116">Related Sections</span></span>  
 <span data-ttu-id="905ef-117">Дополнительные сведения о пространствах имен см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="905ef-117">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="905ef-118">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="905ef-118">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="905ef-119">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="905ef-119">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="905ef-120">Практическое руководство. Использование пространства имен My</span><span class="sxs-lookup"><span data-stu-id="905ef-120">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="905ef-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="905ef-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="905ef-122">См. также</span><span class="sxs-lookup"><span data-stu-id="905ef-122">See Also</span></span>  
 [<span data-ttu-id="905ef-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="905ef-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="905ef-124">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="905ef-124">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="905ef-125">Директива using</span><span class="sxs-lookup"><span data-stu-id="905ef-125">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="905ef-126">Оператор ::</span><span class="sxs-lookup"><span data-stu-id="905ef-126">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="905ef-127">. Оператор</span><span class="sxs-lookup"><span data-stu-id="905ef-127">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
