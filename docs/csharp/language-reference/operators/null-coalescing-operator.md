---
title: ?? Оператор. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 153accdc4995065563b00da0fd62992341c06cf1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241883"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="55b4c-103">??</span><span class="sxs-lookup"><span data-stu-id="55b4c-103">??</span></span> <span data-ttu-id="55b4c-104">Оператор (ссылка C#)</span><span class="sxs-lookup"><span data-stu-id="55b4c-104">Operator (C# Reference)</span></span>
<span data-ttu-id="55b4c-105">Оператор `??` называется оператором объединения со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="55b4c-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="55b4c-106">Он возвращает левый операнд, если этот операнд не имеет значение NULL; в противном случае возвращается правый операнд.</span><span class="sxs-lookup"><span data-stu-id="55b4c-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55b4c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="55b4c-107">Remarks</span></span>  
 <span data-ttu-id="55b4c-108">Тип, допускающий значение NULL, может представлять значение из домена типа или иметь неопределенное значение (в последнем случае значение равно NULL).</span><span class="sxs-lookup"><span data-stu-id="55b4c-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="55b4c-109">Синтаксические возможности оператора `??` можно использовать для возврата соответствующего значения (правого операнда), если тип левого операнда допускает значение NULL и левый операнд имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="55b4c-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="55b4c-110">Если без использования оператора `??` попытаться присвоить тип, допускающий значение NULL, типу, не допускающему такое значение, то во время компиляции появится ошибка.</span><span class="sxs-lookup"><span data-stu-id="55b4c-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="55b4c-111">Если используется приведение типов и допускающий значение NULL тип в данный момент не определен, будет создано исключение `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="55b4c-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="55b4c-112">Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).</span><span class="sxs-lookup"><span data-stu-id="55b4c-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="55b4c-113">Результат ??</span><span class="sxs-lookup"><span data-stu-id="55b4c-113">The result of a ??</span></span> <span data-ttu-id="55b4c-114">Оператор не считается константой, даже если оба его аргумента являются константами.</span><span class="sxs-lookup"><span data-stu-id="55b4c-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55b4c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="55b4c-115">Example</span></span>  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="55b4c-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="55b4c-116">C# Language Specification</span></span>  

<span data-ttu-id="55b4c-117">Дополнительные сведения см. в разделе [Оператор объединения со значением NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="55b4c-117">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="55b4c-118">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="55b4c-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55b4c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="55b4c-119">See Also</span></span>

- [<span data-ttu-id="55b4c-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="55b4c-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="55b4c-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="55b4c-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="55b4c-122">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="55b4c-122">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="55b4c-123">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="55b4c-123">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
- [<span data-ttu-id="55b4c-124">Что означает термин "расширенные"?</span><span class="sxs-lookup"><span data-stu-id="55b4c-124">What Exactly Does 'Lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
