---
title: Справочник по C#. Оператор ()
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 57c23dbd6ee95597514dba92e7217bdcc3e38f24
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236461"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5f783-102">Оператор () (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5f783-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="5f783-103">Помимо использования для указания порядка операций в выражении круглые скобки используются для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="5f783-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="5f783-104">Задание операций приведения или преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="5f783-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="5f783-105">Вызов методов или делегатов.</span><span class="sxs-lookup"><span data-stu-id="5f783-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="5f783-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f783-106">Remarks</span></span>  
 <span data-ttu-id="5f783-107">Приведение явно вызывает оператор преобразования из одного типа в другой. Если такой оператор преобразования не определен, приведение завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="5f783-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="5f783-108">Сведения об определении оператора преобразования см. в разделах [explicit](../../../csharp/language-reference/keywords/explicit.md) и [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="5f783-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="5f783-109">Оператор `()` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="5f783-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="5f783-110">Дополнительные сведения см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="5f783-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="5f783-111">Дополнительные сведения о вызове методов см. в разделе [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="5f783-111">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5f783-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5f783-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f783-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5f783-113">See Also</span></span>

- [<span data-ttu-id="5f783-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5f783-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5f783-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5f783-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5f783-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="5f783-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
