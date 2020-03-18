---
title: Справочник по C#. Область доступности
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 4a4319b03f3e0d7f9ec721e611b78c124a8a8ee5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713835"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="276a1-102">Область доступности (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="276a1-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="276a1-103">Область доступности члена определяет, в каких разделах программы может присутствовать ссылка на этот член.</span><span class="sxs-lookup"><span data-stu-id="276a1-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="276a1-104">Если член вложен в другой тип, его область доступности определяется как [уровнем доступности](./accessibility-levels.md) самого члена, так и областью доступности типа, непосредственно содержащего вложенный тип.</span><span class="sxs-lookup"><span data-stu-id="276a1-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](./accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="276a1-105">Область доступности типа верхнего уровня — это по крайней мере текст программы проекта, в котором он объявлен.</span><span class="sxs-lookup"><span data-stu-id="276a1-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="276a1-106">То есть область включает в себя все исходные файлы данного проекта.</span><span class="sxs-lookup"><span data-stu-id="276a1-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="276a1-107">Область доступности вложенного типа — это по крайней мере текст программы типа, в котором он объявлен.</span><span class="sxs-lookup"><span data-stu-id="276a1-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="276a1-108">Таким образом, областью является тело типа, включающее все вложенные типы.</span><span class="sxs-lookup"><span data-stu-id="276a1-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="276a1-109">Область доступности вложенного типа никогда не выходит за пределы области доступности содержащего его типа.</span><span class="sxs-lookup"><span data-stu-id="276a1-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="276a1-110">Эти принципы продемонстрированы в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="276a1-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="276a1-111">Пример</span><span class="sxs-lookup"><span data-stu-id="276a1-111">Example</span></span>  
 <span data-ttu-id="276a1-112">Этот пример содержит тип верхнего уровня `T1` и два вложенных класса: `M1` и `M2`.</span><span class="sxs-lookup"><span data-stu-id="276a1-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="276a1-113">Классы содержат поля, имеющие различную объявленную доступность.</span><span class="sxs-lookup"><span data-stu-id="276a1-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="276a1-114">В методе `Main` после каждого оператора следует комментарий, указывающий область доступности для каждого члена.</span><span class="sxs-lookup"><span data-stu-id="276a1-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="276a1-115">Обратите внимание, что операторы, ссылающиеся на недоступные члены, закомментированы. Если необходимо просмотреть сообщения об ошибках, выдаваемые компилятором при попытке обращения к недоступному члену, удаляйте комментарии по одному.</span><span class="sxs-lookup"><span data-stu-id="276a1-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="276a1-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="276a1-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="276a1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="276a1-117">See also</span></span>

- [<span data-ttu-id="276a1-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="276a1-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="276a1-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="276a1-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="276a1-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="276a1-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="276a1-121">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="276a1-121">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="276a1-122">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="276a1-122">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="276a1-123">Ограничения на использование уровней доступности</span><span class="sxs-lookup"><span data-stu-id="276a1-123">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="276a1-124">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="276a1-124">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="276a1-125">public</span><span class="sxs-lookup"><span data-stu-id="276a1-125">public</span></span>](./public.md)
- [<span data-ttu-id="276a1-126">private</span><span class="sxs-lookup"><span data-stu-id="276a1-126">private</span></span>](./private.md)
- [<span data-ttu-id="276a1-127">protected</span><span class="sxs-lookup"><span data-stu-id="276a1-127">protected</span></span>](./protected.md)
- [<span data-ttu-id="276a1-128">internal</span><span class="sxs-lookup"><span data-stu-id="276a1-128">internal</span></span>](./internal.md)
