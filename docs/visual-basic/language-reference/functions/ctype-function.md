---
title: Функция CType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 77bff81efbd61a68c054519710bd671d90af1e7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694780"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="be016-102">Функция CType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be016-102">CType Function (Visual Basic)</span></span>
<span data-ttu-id="be016-103">Возвращает результат явного преобразования выражения для указанного типа данных, объекта, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="be016-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be016-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be016-104">Syntax</span></span>  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a><span data-ttu-id="be016-105">Части</span><span class="sxs-lookup"><span data-stu-id="be016-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="be016-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="be016-106">Any valid expression.</span></span> <span data-ttu-id="be016-107">Если значение `expression` находится за пределами диапазона, разрешенного `typename`, Visual Basic создает исключение.</span><span class="sxs-lookup"><span data-stu-id="be016-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>  
  
 `typename`  
 <span data-ttu-id="be016-108">Любое выражение, которое является допустимым в пределах `As` предложение в `Dim` инструкции, то есть имя типа данных, объекта, структуры, класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="be016-108">Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be016-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="be016-109">Remarks</span></span>  
  
> [!TIP]
>  <span data-ttu-id="be016-110">Для выполнения преобразования типов также можно использовать следующие функции:</span><span class="sxs-lookup"><span data-stu-id="be016-110">You can also use the following functions to perform a type conversion:</span></span>  
>   
>  -   <span data-ttu-id="be016-111">Функции преобразования типа, таких как `CByte`, `CDbl`, и `CInt` , которые выполняют преобразование к определенному типу данных.</span><span class="sxs-lookup"><span data-stu-id="be016-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="be016-112">Дополнительные сведения см. в разделе [функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="be016-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
> -   <span data-ttu-id="be016-113">[Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="be016-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="be016-114">Эти операторы требуют наследовать от одного типа или реализовывал другой тип.</span><span class="sxs-lookup"><span data-stu-id="be016-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="be016-115">Они могут предоставить несколько более высокую производительность, чем `CType` при преобразовании значений с `Object` тип данных.</span><span class="sxs-lookup"><span data-stu-id="be016-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>  
  
 <span data-ttu-id="be016-116">`CType` — компилируется путем подстановки, это означает, что код преобразования является частью кода, вычисляет выражение.</span><span class="sxs-lookup"><span data-stu-id="be016-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="be016-117">В некоторых случаях код выполняется быстрее, так как ни одной процедуры вызываются для выполнения преобразования.</span><span class="sxs-lookup"><span data-stu-id="be016-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>  
  
 <span data-ttu-id="be016-118">Если не определено преобразование из `expression` для `typename` (например, из `Integer` для `Date`), Visual Basic отображает сообщение об ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="be016-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>  
  
 <span data-ttu-id="be016-119">При сбое преобразования во время выполнения, возникает соответствующее исключение.</span><span class="sxs-lookup"><span data-stu-id="be016-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="be016-120">При сбое сужающего преобразования <xref:System.OverflowException> является наиболее распространенным результатом.</span><span class="sxs-lookup"><span data-stu-id="be016-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="be016-121">Если преобразование не определено, <xref:System.InvalidCastException> исключение.</span><span class="sxs-lookup"><span data-stu-id="be016-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="be016-122">Например, это может произойти, если `expression` имеет тип `Object` и его тип времени выполнения не имеет преобразования в `typename`.</span><span class="sxs-lookup"><span data-stu-id="be016-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>  
  
 <span data-ttu-id="be016-123">Если тип данных `expression` или `typename` — это класс или структуру, вы определили, можно определить `CType` для этого класса или структуры в качестве оператора преобразования.</span><span class="sxs-lookup"><span data-stu-id="be016-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="be016-124">Это делает `CType` выступать в качестве *перегруженный оператор*.</span><span class="sxs-lookup"><span data-stu-id="be016-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="be016-125">После этого можно управлять поведением преобразования в и из класса или структуры, включая исключения, которые могут создаваться.</span><span class="sxs-lookup"><span data-stu-id="be016-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="be016-126">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="be016-126">Overloading</span></span>  
 <span data-ttu-id="be016-127">`CType` Оператор также может быть перегружен для класса или структуры, определяемой вне данного кода.</span><span class="sxs-lookup"><span data-stu-id="be016-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="be016-128">Если код осуществляет преобразование в или из такого класса или структуры, убедитесь, что вы понимаете поведение его `CType` оператор.</span><span class="sxs-lookup"><span data-stu-id="be016-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="be016-129">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="be016-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="converting-dynamic-objects"></a><span data-ttu-id="be016-130">Преобразование динамических объектов</span><span class="sxs-lookup"><span data-stu-id="be016-130">Converting Dynamic Objects</span></span>  
 <span data-ttu-id="be016-131">Тип преобразования динамических объектов выполняются через определяемые пользователем преобразованиями, использующего <xref:System.Dynamic.DynamicObject.TryConvert%2A> или <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="be016-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="be016-132">Если вы работаете с динамическими объектами, используйте <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> метод для преобразования динамический объект.</span><span class="sxs-lookup"><span data-stu-id="be016-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be016-133">Пример</span><span class="sxs-lookup"><span data-stu-id="be016-133">Example</span></span>  
 <span data-ttu-id="be016-134">В следующем примере используется `CType` функцию для преобразования выражения `Single` тип данных.</span><span class="sxs-lookup"><span data-stu-id="be016-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 <span data-ttu-id="be016-135">Дополнительные примеры см. в разделе [явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="be016-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be016-136">См. также</span><span class="sxs-lookup"><span data-stu-id="be016-136">See also</span></span>
- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="be016-137">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="be016-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="be016-138">Функции преобразования</span><span class="sxs-lookup"><span data-stu-id="be016-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="be016-139">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="be016-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="be016-140">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="be016-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="be016-141">Преобразование типов в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="be016-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
