---
title: "Тип данных UInteger"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3852bd56d11c19e327e6c2f3e23cfb082a54e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="uinteger-data-type"></a><span data-ttu-id="945b1-102">UInteger - тип данных</span><span class="sxs-lookup"><span data-stu-id="945b1-102">UInteger data type</span></span>

<span data-ttu-id="945b1-103">Содержит 32-разрядные (4-байтовое) целых чисел без знака в диапазоне от 0 до 4 294 967 295.</span><span class="sxs-lookup"><span data-stu-id="945b1-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="945b1-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="945b1-104">Remarks</span></span>

 <span data-ttu-id="945b1-105">`UInteger` Тип данных предоставляет наибольшее значение без знака в наиболее эффективной ширине данных.</span><span class="sxs-lookup"><span data-stu-id="945b1-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="945b1-106">Значение по умолчанию для типа `UInteger` — 0.</span><span class="sxs-lookup"><span data-stu-id="945b1-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="945b1-107">Литерал назначения</span><span class="sxs-lookup"><span data-stu-id="945b1-107">Literal assignments</span></span>

<span data-ttu-id="945b1-108">Можно объявить и инициализировать `UInteger` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="945b1-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="945b1-109">Если целочисленный литерал выходит за пределы диапазона `UInteger` (то есть, если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="945b1-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="945b1-110">В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="945b1-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="945b1-111">Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала.</span><span class="sxs-lookup"><span data-stu-id="945b1-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="945b1-112">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="945b1-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="945b1-113">Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.</span><span class="sxs-lookup"><span data-stu-id="945b1-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="945b1-114">Можно также включать числовые литералы `UI` или `ui` [символ типа](../../programming-guide\language-features\data-types/type-characters.md) для обозначения `UInteger` тип данных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="945b1-114">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H0FAC14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="945b1-115">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="945b1-115">Programming tips</span></span>

 <span data-ttu-id="945b1-116">`UInteger` И `Integer` типы данных обеспечивает оптимальную производительность на 32-разрядный процессор, так как типы меньших целых чисел (`UShort`, `Short`, `Byte`, и `SByte`), даже если они используют меньшее число битов, занимает больше времени Загрузка, хранение и выборку.</span><span class="sxs-lookup"><span data-stu-id="945b1-116">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="945b1-117">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="945b1-117">**Negative Numbers.**</span></span> <span data-ttu-id="945b1-118">Поскольку `UInteger` является тип без знака, он не может представлять отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="945b1-118">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="945b1-119">Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `UInteger`, Visual Basic преобразует выражение, `Long` первой.</span><span class="sxs-lookup"><span data-stu-id="945b1-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="945b1-120">**CLS-совместимости.**</span><span class="sxs-lookup"><span data-stu-id="945b1-120">**CLS Compliance.**</span></span> <span data-ttu-id="945b1-121">`UInteger` Тип данных не является частью [спецификации CLS](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.</span><span class="sxs-lookup"><span data-stu-id="945b1-121">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="945b1-122">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="945b1-122">**Interop Considerations.**</span></span> <span data-ttu-id="945b1-123">При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, имейте в виду, что типы, такие как `uint` может иметь другой размер (16 бит) в других средах.</span><span class="sxs-lookup"><span data-stu-id="945b1-123">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="945b1-124">Если вы передаете 16-разрядного аргумента такому компоненту, объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="945b1-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="945b1-125">**Расширяющие.**</span><span class="sxs-lookup"><span data-stu-id="945b1-125">**Widening.**</span></span> <span data-ttu-id="945b1-126">`UInteger` Тип данных может быть расширен до `Long`, `ULong`, `Decimal`, `Single`, и `Double`.</span><span class="sxs-lookup"><span data-stu-id="945b1-126">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="945b1-127">Это означает, что можно преобразовать `UInteger` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.</span><span class="sxs-lookup"><span data-stu-id="945b1-127">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="945b1-128">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="945b1-128">**Type Characters.**</span></span> <span data-ttu-id="945b1-129">Символы типа литерала добавления `UI` с литералом приводит к принудительному `UInteger` тип данных.</span><span class="sxs-lookup"><span data-stu-id="945b1-129">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="945b1-130">`UInteger`не имеет типа символа идентификатора.</span><span class="sxs-lookup"><span data-stu-id="945b1-130">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="945b1-131">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="945b1-131">**Framework Type.**</span></span> <span data-ttu-id="945b1-132">В .NET Framework данный тип соответствует структуре <xref:System.UInt32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="945b1-132">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945b1-133">См. также</span><span class="sxs-lookup"><span data-stu-id="945b1-133">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="945b1-134">Типы данных</span><span class="sxs-lookup"><span data-stu-id="945b1-134">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="945b1-135">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="945b1-135">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="945b1-136">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="945b1-136">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="945b1-137">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="945b1-137">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="945b1-138">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="945b1-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
