---
title: "Тип данных ULong (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afc52bfd16541feed599d5445adad7aba04f8e9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="9292d-102">Тип данных ULong (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9292d-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="9292d-103">Содержит 64-разрядные (8-байтные) целых чисел без знака в диапазоне от 0 до 18446744073709551615 (1,84 раза больше чем 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="9292d-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9292d-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="9292d-104">Remarks</span></span>

<span data-ttu-id="9292d-105">Используйте `ULong` тип данных для хранения двоичных данных, слишком велик для `UInteger`, или наибольшее возможное без знака целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="9292d-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="9292d-106">Значение по умолчанию для типа `ULong` — 0.</span><span class="sxs-lookup"><span data-stu-id="9292d-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="9292d-107">Литерал назначения</span><span class="sxs-lookup"><span data-stu-id="9292d-107">Literal assignments</span></span>

<span data-ttu-id="9292d-108">Можно объявить и инициализировать `ULong` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="9292d-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="9292d-109">Если целочисленный литерал выходит за пределы диапазона `ULong` (то есть, если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="9292d-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="9292d-110">В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ULong`.</span><span class="sxs-lookup"><span data-stu-id="9292d-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="9292d-111">Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="9292d-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="9292d-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="9292d-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="9292d-113">Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="9292d-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="9292d-114">Можно также включать числовые литералы `UL` или `ul` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `ULong` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9292d-114">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="9292d-115">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="9292d-115">Programming tips</span></span>
  
-   <span data-ttu-id="9292d-116">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="9292d-116">**Negative Numbers.**</span></span> <span data-ttu-id="9292d-117">Поскольку `ULong` является тип без знака, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="9292d-117">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="9292d-118">Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `ULong`, Visual Basic преобразует выражение, `Decimal` первой.</span><span class="sxs-lookup"><span data-stu-id="9292d-118">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
-   <span data-ttu-id="9292d-119">**CLS-совместимости.**</span><span class="sxs-lookup"><span data-stu-id="9292d-119">**CLS Compliance.**</span></span> <span data-ttu-id="9292d-120">`ULong` Тип данных не является частью [спецификации CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="9292d-120">The `ULong` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
-   <span data-ttu-id="9292d-121">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="9292d-121">**Interop Considerations.**</span></span> <span data-ttu-id="9292d-122">При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, имейте в виду, что типы, такие как `ulong` может иметь другой размер (32 бита) в других средах.</span><span class="sxs-lookup"><span data-stu-id="9292d-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="9292d-123">Если вы передаете 32-разрядного аргумента такому компоненту, объявите его как `UInteger` вместо `ULong` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9292d-123">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="9292d-124">Кроме того Automation не поддерживает 64-битовых целых чисел в Windows 95, Windows 98, Windows ME или Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="9292d-124">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="9292d-125">Невозможно передать Visual Basic `ULong` аргумент компоненту автоматизации на этих платформах.</span><span class="sxs-lookup"><span data-stu-id="9292d-125">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
-   <span data-ttu-id="9292d-126">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="9292d-126">**Widening.**</span></span> <span data-ttu-id="9292d-127">`ULong` Тип данных может быть расширен до `Decimal`, `Single`, и `Double`.</span><span class="sxs-lookup"><span data-stu-id="9292d-127">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="9292d-128">Это означает, что можно преобразовать `ULong` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="9292d-128">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="9292d-129">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="9292d-129">**Type Characters.**</span></span> <span data-ttu-id="9292d-130">Символы типа литерала добавления `UL` с литералом приводит к принудительному `ULong` тип данных.</span><span class="sxs-lookup"><span data-stu-id="9292d-130">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="9292d-131">`ULong`не имеет типа символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="9292d-131">`ULong` has no identifier type character.</span></span>
  
-   <span data-ttu-id="9292d-132">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="9292d-132">**Framework Type.**</span></span> <span data-ttu-id="9292d-133">В .NET Framework данный тип соответствует структуре <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9292d-133">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9292d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9292d-134">See also</span></span>

 <xref:System.UInt64>  
 [<span data-ttu-id="9292d-135">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9292d-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="9292d-136">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="9292d-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="9292d-137">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="9292d-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="9292d-138">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="9292d-138">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="9292d-139">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="9292d-139">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
