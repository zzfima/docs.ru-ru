---
title: "Область доступности (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
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
ms.openlocfilehash: 90faf22d8a7d515ae8bd062f0b95f4be5e051f79
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="f7845-102">Область доступности (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f7845-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="f7845-103">Область доступности члена определяет, в каких разделах программы может присутствовать ссылка на этот член.</span><span class="sxs-lookup"><span data-stu-id="f7845-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="f7845-104">Если член вложен в другой тип, его область доступности определяется как [уровнем доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) самого члена, так и областью доступности типа, непосредственно содержащего вложенный тип.</span><span class="sxs-lookup"><span data-stu-id="f7845-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="f7845-105">Область доступности типа верхнего уровня — это по крайней мере текст программы проекта, в котором он объявлен.</span><span class="sxs-lookup"><span data-stu-id="f7845-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="f7845-106">То есть область включает в себя все исходные файлы данного проекта.</span><span class="sxs-lookup"><span data-stu-id="f7845-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="f7845-107">Область доступности вложенного типа — это по крайней мере текст программы типа, в котором он объявлен.</span><span class="sxs-lookup"><span data-stu-id="f7845-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="f7845-108">Таким образом, областью является тело типа, включающее все вложенные типы.</span><span class="sxs-lookup"><span data-stu-id="f7845-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="f7845-109">Область доступности вложенного типа никогда не выходит за пределы области доступности содержащего его типа.</span><span class="sxs-lookup"><span data-stu-id="f7845-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="f7845-110">Эти принципы продемонстрированы в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="f7845-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7845-111">Пример</span><span class="sxs-lookup"><span data-stu-id="f7845-111">Example</span></span>  
 <span data-ttu-id="f7845-112">Этот пример содержит тип верхнего уровня `T1` и два вложенных класса: `M1` и `M2`.</span><span class="sxs-lookup"><span data-stu-id="f7845-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="f7845-113">Классы содержат поля, имеющие различную объявленную доступность.</span><span class="sxs-lookup"><span data-stu-id="f7845-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="f7845-114">В методе `Main` после каждого оператора следует комментарий, указывающий область доступности для каждого члена.</span><span class="sxs-lookup"><span data-stu-id="f7845-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="f7845-115">Обратите внимание, что операторы, ссылающиеся на недоступные члены, закомментированы.</span><span class="sxs-lookup"><span data-stu-id="f7845-115">Notice that the statements that try to reference the inaccessible members are commented out.</span></span> <span data-ttu-id="f7845-116">Если необходимо просмотреть сообщения об ошибках, выдаваемые компилятором при попытке обращения к недоступному члену, удаляйте комментарии по одному.</span><span class="sxs-lookup"><span data-stu-id="f7845-116">If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
 <span data-ttu-id="f7845-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7845-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f7845-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f7845-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f7845-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f7845-119">See Also</span></span>  
 <span data-ttu-id="f7845-120">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f7845-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f7845-122">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f7845-123">[Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-123">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="f7845-124">[Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-124">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="f7845-125">[Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-125">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="f7845-126">[Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="f7845-127">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-127">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="f7845-128">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-128">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="f7845-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="f7845-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="f7845-130">internal</span><span class="sxs-lookup"><span data-stu-id="f7845-130">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

