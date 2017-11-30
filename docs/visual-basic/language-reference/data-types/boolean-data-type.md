---
title: "Тип данных Boolean (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdc106f1ec874c1a2165df069d5f3485fe5b2e43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="15bb7-102">Тип данных Boolean (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15bb7-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="15bb7-103">Содержит значения, которые могут быть только `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="15bb7-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="15bb7-104">Ключевые слова `True` и `False` соответствуют двух состояний `Boolean` переменных.</span><span class="sxs-lookup"><span data-stu-id="15bb7-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15bb7-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="15bb7-105">Remarks</span></span>  
 <span data-ttu-id="15bb7-106">Используйте [логический тип данных (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) содержит два значения состояния, например true или false, Да/Нет или Вкл/Выкл.</span><span class="sxs-lookup"><span data-stu-id="15bb7-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="15bb7-107">Значением свойства `Boolean` по умолчанию является `False`.</span><span class="sxs-lookup"><span data-stu-id="15bb7-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="15bb7-108">`Boolean`значения не хранятся в виде чисел, и хранимые значения не должны быть эквивалентными числам.</span><span class="sxs-lookup"><span data-stu-id="15bb7-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="15bb7-109">Никогда не следует писать код, который основывается на эквивалентных числовых значениях для `True` и `False`.</span><span class="sxs-lookup"><span data-stu-id="15bb7-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="15bb7-110">Когда это возможно, следует ограничить использование `Boolean` переменные с логическими значениями, для которых они предназначены.</span><span class="sxs-lookup"><span data-stu-id="15bb7-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="15bb7-111">Преобразования типов</span><span class="sxs-lookup"><span data-stu-id="15bb7-111">Type Conversions</span></span>  
 <span data-ttu-id="15bb7-112">Когда Visual Basic преобразует числовые значения данных, тип `Boolean`, 0 становится `False` и все остальные значения становятся `True`.</span><span class="sxs-lookup"><span data-stu-id="15bb7-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="15bb7-113">Когда Visual Basic преобразует `Boolean` значения в числовые типы `False` становится 0 и `True` становится 1.</span><span class="sxs-lookup"><span data-stu-id="15bb7-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="15bb7-114">При преобразовании между `Boolean` значения и числовые типы данных, следует помнить, что методы преобразования платформы .NET Framework не всегда производят те же результаты, как ключевые слова преобразования Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15bb7-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="15bb7-115">Это так, как преобразование Visual Basic сохраняет поведение, совместимое с предыдущими версиями.</span><span class="sxs-lookup"><span data-stu-id="15bb7-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="15bb7-116">Дополнительные сведения см. в разделе «Логическое тип Does не преобразования для числового типа точно» в [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="15bb7-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="15bb7-117">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="15bb7-117">Programming Tips</span></span>  
  
-   <span data-ttu-id="15bb7-118">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="15bb7-118">**Negative Numbers.**</span></span> <span data-ttu-id="15bb7-119">`Boolean`не является числовым типом и не может представлять отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="15bb7-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="15bb7-120">В любом случае не следует использовать `Boolean` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="15bb7-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="15bb7-121">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="15bb7-121">**Type Characters.**</span></span> <span data-ttu-id="15bb7-122">`Boolean`не имеет знак типа литерала или знак типа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="15bb7-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="15bb7-123">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="15bb7-123">**Framework Type.**</span></span> <span data-ttu-id="15bb7-124">В .NET Framework данный тип соответствует структуре <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15bb7-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15bb7-125">Пример</span><span class="sxs-lookup"><span data-stu-id="15bb7-125">Example</span></span>  
 <span data-ttu-id="15bb7-126">В следующем примере `runningVB` — `Boolean` переменной, которая хранит простой Да/нет.</span><span class="sxs-lookup"><span data-stu-id="15bb7-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="15bb7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="15bb7-127">See Also</span></span>  
 <xref:System.Boolean?displayProperty=nameWithType>  
 [<span data-ttu-id="15bb7-128">Типы данных</span><span class="sxs-lookup"><span data-stu-id="15bb7-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="15bb7-129">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="15bb7-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="15bb7-130">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="15bb7-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="15bb7-131">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="15bb7-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="15bb7-132">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="15bb7-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="15bb7-133">Функция CType</span><span class="sxs-lookup"><span data-stu-id="15bb7-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
