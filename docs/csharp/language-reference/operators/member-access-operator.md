---
title: ". Оператор (ссылка C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ._CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
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
ms.openlocfilehash: fdc7c1821548509f3a3750aef2836c034f7aa53b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="fae22-103">.</span><span class="sxs-lookup"><span data-stu-id="fae22-103">.</span></span> <span data-ttu-id="fae22-104">Оператор (ссылка C#)</span><span class="sxs-lookup"><span data-stu-id="fae22-104">Operator (C# Reference)</span></span>
<span data-ttu-id="fae22-105">Оператор "точка" (`.`) используется для доступа к членам.</span><span class="sxs-lookup"><span data-stu-id="fae22-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="fae22-106">Он определяет член типа или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fae22-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="fae22-107">Например, оператор "точка" используется для доступа к определенным методам в библиотеках классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fae22-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 <span data-ttu-id="fae22-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fae22-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="fae22-109">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="fae22-109">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="fae22-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fae22-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="fae22-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fae22-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="fae22-112">Переменная `s` имеет два члена: `a` и `b`. Чтобы получить к ним доступ, используйте оператор "точка".</span><span class="sxs-lookup"><span data-stu-id="fae22-112">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 <span data-ttu-id="fae22-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fae22-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="fae22-114">Точка также используется для формирования полных имен, указывающих пространство имен или интерфейс, к которым они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="fae22-114">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 <span data-ttu-id="fae22-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="fae22-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="fae22-116">Директива using делает уточнение некоторых имен необязательным.</span><span class="sxs-lookup"><span data-stu-id="fae22-116">The using directive makes some name qualification optional:</span></span>  
  
 <span data-ttu-id="fae22-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="fae22-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span></span>  
  
 <span data-ttu-id="fae22-118">Однако в случае неоднозначного идентификатора имя должно быть полным.</span><span class="sxs-lookup"><span data-stu-id="fae22-118">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 <span data-ttu-id="fae22-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="fae22-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fae22-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fae22-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fae22-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fae22-121">See Also</span></span>  
 <span data-ttu-id="fae22-122">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fae22-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fae22-123">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fae22-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="fae22-124">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="fae22-124">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

