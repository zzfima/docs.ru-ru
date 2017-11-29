---
title: "Тип данных UShort (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513e8ce4694788d33c5aa14e34b95e88b6d37ff1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="84b24-102">Тип данных UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b24-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="84b24-103">Содержит 16-разрядное (2-байтовые) целых чисел без знака в диапазоне от 0 до 65 535.</span><span class="sxs-lookup"><span data-stu-id="84b24-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84b24-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="84b24-104">Remarks</span></span>

 <span data-ttu-id="84b24-105">Используйте `UShort` тип данных для хранения двоичных данных, слишком велик для `Byte`.</span><span class="sxs-lookup"><span data-stu-id="84b24-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="84b24-106">Значение по умолчанию для типа `UShort` — 0.</span><span class="sxs-lookup"><span data-stu-id="84b24-106">The default value of `UShort` is 0.</span></span>  

# <a name="literal-assignments"></a><span data-ttu-id="84b24-107">Литерал назначения</span><span class="sxs-lookup"><span data-stu-id="84b24-107">Literal assignments</span></span>

<span data-ttu-id="84b24-108">Можно объявить и инициализировать `UShort` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="84b24-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="84b24-109">Если целочисленный литерал выходит за пределы диапазона `UShort` (то есть, если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="84b24-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="84b24-110">В следующем примере целых чисел, равные 65,034, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы назначены `UShort` значения.</span><span class="sxs-lookup"><span data-stu-id="84b24-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="84b24-111">Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="84b24-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="84b24-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="84b24-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="84b24-113">Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="84b24-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="84b24-114">Можно также включать числовые литералы `US` или `us` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `UShort` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="84b24-114">Numeric literals can also include the `US` or `us` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H035826us
```

## <a name="programming-tips"></a><span data-ttu-id="84b24-115">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="84b24-115">Programming tips</span></span>
  
-   <span data-ttu-id="84b24-116">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="84b24-116">**Negative Numbers.**</span></span> <span data-ttu-id="84b24-117">Поскольку `UShort` является тип без знака, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="84b24-117">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="84b24-118">Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `UShort`, Visual Basic преобразует выражение, `Integer` первой.</span><span class="sxs-lookup"><span data-stu-id="84b24-118">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="84b24-119">**CLS-совместимости.**</span><span class="sxs-lookup"><span data-stu-id="84b24-119">**CLS Compliance.**</span></span> <span data-ttu-id="84b24-120">`UShort` Тип данных не является частью [спецификации CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="84b24-120">The `UShort` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="84b24-121">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="84b24-121">**Widening.**</span></span> <span data-ttu-id="84b24-122">`UShort` Тип данных может быть расширен до `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, и `Double`.</span><span class="sxs-lookup"><span data-stu-id="84b24-122">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="84b24-123">Это означает, что можно преобразовать `UShort` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="84b24-123">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="84b24-124">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="84b24-124">**Type Characters.**</span></span> <span data-ttu-id="84b24-125">Символы типа литерала добавления `US` с литералом приводит к принудительному `UShort` тип данных.</span><span class="sxs-lookup"><span data-stu-id="84b24-125">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="84b24-126">`UShort`не имеет типа символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="84b24-126">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="84b24-127">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="84b24-127">**Framework Type.**</span></span> <span data-ttu-id="84b24-128">В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84b24-128">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b24-129">См. также</span><span class="sxs-lookup"><span data-stu-id="84b24-129">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="84b24-130">Типы данных</span><span class="sxs-lookup"><span data-stu-id="84b24-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="84b24-131">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="84b24-131">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="84b24-132">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="84b24-132">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="84b24-133">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="84b24-133">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="84b24-134">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="84b24-134">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
