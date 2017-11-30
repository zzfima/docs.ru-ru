---
title: "?? Оператор (ссылка C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a49d36b8580812c08e9ee080a9602d9fc2027ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a9a0c-103">??</span><span class="sxs-lookup"><span data-stu-id="a9a0c-103">??</span></span> <span data-ttu-id="a9a0c-104">Оператор (ссылка C#)</span><span class="sxs-lookup"><span data-stu-id="a9a0c-104">Operator (C# Reference)</span></span>
<span data-ttu-id="a9a0c-105">Оператор `??` называется оператором объединения со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="a9a0c-106">Он возвращает левый операнд, если этот операнд не имеет значение NULL; в противном случае возвращается правый операнд.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9a0c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9a0c-107">Remarks</span></span>  
 <span data-ttu-id="a9a0c-108">Тип, допускающий значение NULL, может представлять значение из домена типа или иметь неопределенное значение (в последнем случае значение равно NULL).</span><span class="sxs-lookup"><span data-stu-id="a9a0c-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="a9a0c-109">Можно использовать `??` синтаксические возможности оператора для возврата соответствующего значения (правого операнда) Если левый операнд имеет тип nullable, значение которого равно null.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="a9a0c-110">Если без использования оператора `??` попытаться присвоить тип, допускающий значение NULL, типу, не допускающему такое значение, то во время компиляции появится ошибка.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="a9a0c-111">Если используется приведение типов и допускающий значение NULL тип в данный момент не определен, будет создано исключение `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="a9a0c-112">Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).</span><span class="sxs-lookup"><span data-stu-id="a9a0c-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="a9a0c-113">Результат ??</span><span class="sxs-lookup"><span data-stu-id="a9a0c-113">The result of a ??</span></span> <span data-ttu-id="a9a0c-114">Оператор не считается константой, даже если оба его аргумента являются константами.</span><span class="sxs-lookup"><span data-stu-id="a9a0c-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9a0c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="a9a0c-115">Example</span></span>  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a9a0c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a9a0c-116">See Also</span></span>  
 [<span data-ttu-id="a9a0c-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a9a0c-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a9a0c-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a9a0c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a9a0c-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="a9a0c-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="a9a0c-120">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="a9a0c-120">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="a9a0c-121">Что означает термин "расширенные"?</span><span class="sxs-lookup"><span data-stu-id="a9a0c-121">What Exactly Does 'Lifted' mean?</span></span>](http://go.microsoft.com/fwlink/?LinkID=112382)
