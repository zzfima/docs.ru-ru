---
title: "?? Оператор (ссылка C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ??_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
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
ms.openlocfilehash: 86e50b97d7ded8adc74f031faf026b69ccdd0c87
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="5f3d5-103">??</span><span class="sxs-lookup"><span data-stu-id="5f3d5-103">??</span></span> <span data-ttu-id="5f3d5-104">Оператор (ссылка C#)</span><span class="sxs-lookup"><span data-stu-id="5f3d5-104">Operator (C# Reference)</span></span>
<span data-ttu-id="5f3d5-105">Оператор `??` называется оператором объединения со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="5f3d5-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="5f3d5-106">Он возвращает левый операнд, если этот операнд не имеет значение NULL; в противном случае возвращается правый операнд.</span><span class="sxs-lookup"><span data-stu-id="5f3d5-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f3d5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f3d5-107">Remarks</span></span>  
 <span data-ttu-id="5f3d5-108">Тип, допускающий значение NULL, может представлять значение из домена типа или иметь неопределенное значение (в последнем случае значение равно NULL).</span><span class="sxs-lookup"><span data-stu-id="5f3d5-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="5f3d5-109">Синтаксические возможности оператора `??` можно использовать для возврата соответствующего значения (правого операнда), если тип левого операнда допускает значение NULL и левый операнд имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="5f3d5-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullible type whose value is null.</span></span> <span data-ttu-id="5f3d5-110">Если без использования оператора `??` попытаться присвоить тип, допускающий значение NULL, типу, не допускающему такое значение, то во время компиляции появится ошибка.</span><span class="sxs-lookup"><span data-stu-id="5f3d5-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="5f3d5-111">Если используется приведение типов и допускающий значение NULL тип в данный момент не определен, будет создано исключение `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="5f3d5-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="5f3d5-112">Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).</span><span class="sxs-lookup"><span data-stu-id="5f3d5-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="5f3d5-113">Результат ??</span><span class="sxs-lookup"><span data-stu-id="5f3d5-113">The result of a ??</span></span> <span data-ttu-id="5f3d5-114">Оператор не считается константой, даже если оба его аргумента являются константами.</span><span class="sxs-lookup"><span data-stu-id="5f3d5-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f3d5-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5f3d5-115">Example</span></span>  
 <span data-ttu-id="5f3d5-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5f3d5-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3d5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5f3d5-117">See Also</span></span>  
 <span data-ttu-id="5f3d5-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f3d5-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5f3d5-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f3d5-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5f3d5-120">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f3d5-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="5f3d5-121">[Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="5f3d5-121">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="5f3d5-122">Что означает термин "расширенные"?</span><span class="sxs-lookup"><span data-stu-id="5f3d5-122">What Exactly Does 'Lifted' mean?</span></span>](http://go.microsoft.com/fwlink/?LinkID=112382)

