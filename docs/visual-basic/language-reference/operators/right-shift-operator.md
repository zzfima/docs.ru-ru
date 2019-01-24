---
title: '&gt;&gt; Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: e1d2b6569e2bcb3c1516dbc8c78adca0855481e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668500"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="7c292-102">&gt;&gt; Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c292-102">&gt;&gt; Operator (Visual Basic)</span></span>
<span data-ttu-id="7c292-103">Выполняет арифметическое смещение вправо для битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="7c292-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c292-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c292-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="7c292-105">Части</span><span class="sxs-lookup"><span data-stu-id="7c292-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7c292-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7c292-106">Required.</span></span> <span data-ttu-id="7c292-107">Целое числовое значение.</span><span class="sxs-lookup"><span data-stu-id="7c292-107">Integral numeric value.</span></span> <span data-ttu-id="7c292-108">Результат сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="7c292-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="7c292-109">Тип данных является таким же, как `pattern`.</span><span class="sxs-lookup"><span data-stu-id="7c292-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="7c292-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7c292-110">Required.</span></span> <span data-ttu-id="7c292-111">Целое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="7c292-111">Integral numeric expression.</span></span> <span data-ttu-id="7c292-112">Битовый шаблон должны сдвигаться.</span><span class="sxs-lookup"><span data-stu-id="7c292-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="7c292-113">Тип данных должен быть целочисленный тип (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="7c292-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="7c292-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7c292-114">Required.</span></span> <span data-ttu-id="7c292-115">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="7c292-115">Numeric expression.</span></span> <span data-ttu-id="7c292-116">Количество битов для сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="7c292-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="7c292-117">Тип данных должен быть `Integer` или расширяющего преобразования к `Integer`.</span><span class="sxs-lookup"><span data-stu-id="7c292-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c292-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c292-118">Remarks</span></span>  
 <span data-ttu-id="7c292-119">Арифметические сдвиги не являются циклическими, это означает, что биты, сдвигаемые результата, не подставляются на другом конце.</span><span class="sxs-lookup"><span data-stu-id="7c292-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="7c292-120">В арифметического сдвига вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а бит крайнего левого (знак) передается в позиции битов, освобожденные слева.</span><span class="sxs-lookup"><span data-stu-id="7c292-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="7c292-121">Это означает, что если `pattern` имеет отрицательное значение, освобождаемые устанавливается один; в противном случае они равны нулю.</span><span class="sxs-lookup"><span data-stu-id="7c292-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="7c292-122">Обратите внимание, что типы данных `Byte`, `UShort`, `UInteger`, и `ULong` являются числа без знака, поэтому не знаковый бит для распространения.</span><span class="sxs-lookup"><span data-stu-id="7c292-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="7c292-123">Если `pattern` имеет любой без знака типа, освобождаемые всегда присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="7c292-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="7c292-124">Чтобы предотвратить сдвиг на количество битов, чем результат, Visual Basic маскирует значение `amount` с маской размер, соответствующий тип данных `pattern`.</span><span class="sxs-lookup"><span data-stu-id="7c292-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="7c292-125">Двоичное AND этих значений используется для сдвига.</span><span class="sxs-lookup"><span data-stu-id="7c292-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="7c292-126">Далее приведены маски размера.</span><span class="sxs-lookup"><span data-stu-id="7c292-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="7c292-127">Тип данных `pattern`</span><span class="sxs-lookup"><span data-stu-id="7c292-127">Data type of `pattern`</span></span>|<span data-ttu-id="7c292-128">Размер маски (десятичное)</span><span class="sxs-lookup"><span data-stu-id="7c292-128">Size mask (decimal)</span></span>|<span data-ttu-id="7c292-129">Размер маски (шестнадцатеричный)</span><span class="sxs-lookup"><span data-stu-id="7c292-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="7c292-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="7c292-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="7c292-131">7</span><span class="sxs-lookup"><span data-stu-id="7c292-131">7</span></span>|<span data-ttu-id="7c292-132">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="7c292-132">&H00000007</span></span>|  
|<span data-ttu-id="7c292-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="7c292-133">`Short`, `UShort`</span></span>|<span data-ttu-id="7c292-134">15</span><span class="sxs-lookup"><span data-stu-id="7c292-134">15</span></span>|<span data-ttu-id="7c292-135">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="7c292-135">&H0000000F</span></span>|  
|<span data-ttu-id="7c292-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="7c292-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="7c292-137">31</span><span class="sxs-lookup"><span data-stu-id="7c292-137">31</span></span>|<span data-ttu-id="7c292-138">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="7c292-138">&H0000001F</span></span>|  
|<span data-ttu-id="7c292-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="7c292-139">`Long`, `ULong`</span></span>|<span data-ttu-id="7c292-140">63</span><span class="sxs-lookup"><span data-stu-id="7c292-140">63</span></span>|<span data-ttu-id="7c292-141">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="7c292-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="7c292-142">Если `amount` равно нулю, значение `result` идентично значению `pattern`.</span><span class="sxs-lookup"><span data-stu-id="7c292-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="7c292-143">Если `amount` имеет отрицательное значение, он берется значение без знака и маскируется соответствующий размер маски.</span><span class="sxs-lookup"><span data-stu-id="7c292-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="7c292-144">Арифметические сдвиги никогда не создают исключения переполнения.</span><span class="sxs-lookup"><span data-stu-id="7c292-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7c292-145">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="7c292-145">Overloading</span></span>  
 <span data-ttu-id="7c292-146">`>>` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7c292-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7c292-147">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="7c292-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7c292-148">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7c292-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c292-149">Пример</span><span class="sxs-lookup"><span data-stu-id="7c292-149">Example</span></span>  
 <span data-ttu-id="7c292-150">В следующем примере используется `>>` оператор для выполнения арифметических при сдвиге вправо целых значений.</span><span class="sxs-lookup"><span data-stu-id="7c292-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="7c292-151">Результат всегда имеет тот же тип данных, выражения был перемещен.</span><span class="sxs-lookup"><span data-stu-id="7c292-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 <span data-ttu-id="7c292-152">Далее приведены результаты в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="7c292-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="7c292-153">`result1` является 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="7c292-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="7c292-154">`result2` равно 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="7c292-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="7c292-155">`result3` -2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="7c292-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="7c292-156">`result4` — 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="7c292-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="7c292-157">`result5` значение 0 (сдвигаются 15 разрядов справа).</span><span class="sxs-lookup"><span data-stu-id="7c292-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="7c292-158">Величина сдвига для `result4` вычисляется как 18 и 15, что соответствует 2.</span><span class="sxs-lookup"><span data-stu-id="7c292-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="7c292-159">В следующем примере показано арифметические сдвиги на отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="7c292-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 <span data-ttu-id="7c292-160">Далее приведены результаты в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="7c292-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="7c292-161">`negresult1` — -512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="7c292-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="7c292-162">`negresult2` -1 (распространяется знаковым битом).</span><span class="sxs-lookup"><span data-stu-id="7c292-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c292-163">См. также</span><span class="sxs-lookup"><span data-stu-id="7c292-163">See also</span></span>
- [<span data-ttu-id="7c292-164">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="7c292-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="7c292-165">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="7c292-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="7c292-166">Оператор >>=</span><span class="sxs-lookup"><span data-stu-id="7c292-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="7c292-167">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7c292-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7c292-168">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="7c292-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7c292-169">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7c292-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
