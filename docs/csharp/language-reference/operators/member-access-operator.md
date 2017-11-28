---
title: ". Оператор (ссылка C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2bb636bc110f57ace9a824a43afdd86246ed0a5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9ab07-103">.</span><span class="sxs-lookup"><span data-stu-id="9ab07-103">.</span></span> <span data-ttu-id="9ab07-104">Оператор (ссылка C#)</span><span class="sxs-lookup"><span data-stu-id="9ab07-104">Operator (C# Reference)</span></span>
<span data-ttu-id="9ab07-105">Оператор "точка" (`.`) используется для доступа к членам.</span><span class="sxs-lookup"><span data-stu-id="9ab07-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="9ab07-106">Он определяет член типа или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9ab07-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="9ab07-107">Например, оператор "точка" используется для доступа к определенным методам в библиотеках классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ab07-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 [!code-csharp[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 <span data-ttu-id="9ab07-108">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="9ab07-108">For example, consider the following class:</span></span>  
  
 [!code-csharp[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-csharp[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 <span data-ttu-id="9ab07-109">Переменная `s` имеет два члена: `a` и `b`. Чтобы получить к ним доступ, используйте оператор "точка".</span><span class="sxs-lookup"><span data-stu-id="9ab07-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 [!code-csharp[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 <span data-ttu-id="9ab07-110">Точка также используется для формирования полных имен, указывающих пространство имен или интерфейс, к которым они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="9ab07-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 [!code-csharp[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 <span data-ttu-id="9ab07-111">Директива using делает уточнение некоторых имен необязательным.</span><span class="sxs-lookup"><span data-stu-id="9ab07-111">The using directive makes some name qualification optional:</span></span>  
  
 [!code-csharp[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 <span data-ttu-id="9ab07-112">Однако в случае неоднозначного идентификатора имя должно быть полным.</span><span class="sxs-lookup"><span data-stu-id="9ab07-112">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 [!code-csharp[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="9ab07-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9ab07-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9ab07-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9ab07-114">See Also</span></span>  
 [<span data-ttu-id="9ab07-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9ab07-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9ab07-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9ab07-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9ab07-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="9ab07-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
