---
title: Руководство по программированию на C#. Пространства имен
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 79b7057b1f6a9cdba2215124160b28efb9a1c0be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629517"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="4acac-102">Пространства имен (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="4acac-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="4acac-103">Пространства имен часто используются в программировании на C# двумя способами.</span><span class="sxs-lookup"><span data-stu-id="4acac-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="4acac-104">Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4acac-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="4acac-105">`System` является пространством имен, а `Console` — это класс в нем.</span><span class="sxs-lookup"><span data-stu-id="4acac-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="4acac-106">Можно использовать ключевое слово `using`, и тогда полное имя не потребуется. См. следующий пример:</span><span class="sxs-lookup"><span data-stu-id="4acac-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="4acac-107">См. дополнительные сведения о [директиве using](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="4acac-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="4acac-108">Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах.</span><span class="sxs-lookup"><span data-stu-id="4acac-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="4acac-109">Используйте ключевое слово [namespace](../../language-reference/keywords/namespace.md), чтобы объявить пространство имен, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4acac-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="4acac-110">Имя пространства имен должно быть допустимым [именем идентификатора](../inside-a-program/identifier-names.md) C#.</span><span class="sxs-lookup"><span data-stu-id="4acac-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="4acac-111">Обзор пространств имен</span><span class="sxs-lookup"><span data-stu-id="4acac-111">Namespaces Overview</span></span>  

<span data-ttu-id="4acac-112">Пространства имен имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="4acac-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="4acac-113">Они помогают упорядочивать проекты с большим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="4acac-113">They organize large code projects.</span></span>  
- <span data-ttu-id="4acac-114">Они разделяются оператором `.`.</span><span class="sxs-lookup"><span data-stu-id="4acac-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="4acac-115">Директива `using` позволяет не указывать название пространства имен для каждого класса.</span><span class="sxs-lookup"><span data-stu-id="4acac-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="4acac-116">Пространство имен `global` является корневым: `global::System` всегда будет ссылаться на пространство имен <xref:System> в .NET.</span><span class="sxs-lookup"><span data-stu-id="4acac-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="4acac-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4acac-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4acac-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4acac-118">See also</span></span>

- [<span data-ttu-id="4acac-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4acac-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4acac-120">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="4acac-120">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="4acac-121">Практическое руководство. Использование псевдонима глобального пространства имен</span><span class="sxs-lookup"><span data-stu-id="4acac-121">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="4acac-122">Практическое руководство. Использование пространства имен My</span><span class="sxs-lookup"><span data-stu-id="4acac-122">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="4acac-123">Имена идентификаторов</span><span class="sxs-lookup"><span data-stu-id="4acac-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="4acac-124">Директива using</span><span class="sxs-lookup"><span data-stu-id="4acac-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="4acac-125">:: Оператор</span><span class="sxs-lookup"><span data-stu-id="4acac-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
