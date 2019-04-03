---
title: '>> Operator (Visual Basic)'
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
ms.openlocfilehash: 8803dc2e25edde756958a243d429dd30c5c78bcf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816971"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="46945-102">>> Оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46945-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="46945-103">Выполняет арифметическое смещение вправо для битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="46945-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46945-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46945-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="46945-105">Части</span><span class="sxs-lookup"><span data-stu-id="46945-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="46945-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="46945-106">Required.</span></span> <span data-ttu-id="46945-107">Целое числовое значение.</span><span class="sxs-lookup"><span data-stu-id="46945-107">Integral numeric value.</span></span> <span data-ttu-id="46945-108">Результат сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="46945-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="46945-109">Тип данных является таким же, как `pattern`.</span><span class="sxs-lookup"><span data-stu-id="46945-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="46945-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="46945-110">Required.</span></span> <span data-ttu-id="46945-111">Целое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="46945-111">Integral numeric expression.</span></span> <span data-ttu-id="46945-112">Битовый шаблон должны сдвигаться.</span><span class="sxs-lookup"><span data-stu-id="46945-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="46945-113">Тип данных должен быть целочисленный тип (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="46945-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="46945-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="46945-114">Required.</span></span> <span data-ttu-id="46945-115">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="46945-115">Numeric expression.</span></span> <span data-ttu-id="46945-116">Количество битов для сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="46945-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="46945-117">Тип данных должен быть `Integer` или расширяющего преобразования к `Integer`.</span><span class="sxs-lookup"><span data-stu-id="46945-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46945-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="46945-118">Remarks</span></span>  
 <span data-ttu-id="46945-119">Арифметические сдвиги не являются циклическими, это означает, что биты, сдвигаемые результата, не подставляются на другом конце.</span><span class="sxs-lookup"><span data-stu-id="46945-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="46945-120">В арифметического сдвига вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а бит крайнего левого (знак) передается в позиции битов, освобожденные слева.</span><span class="sxs-lookup"><span data-stu-id="46945-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="46945-121">Это означает, что если `pattern` имеет отрицательное значение, освобождаемые устанавливается один; в противном случае они равны нулю.</span><span class="sxs-lookup"><span data-stu-id="46945-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="46945-122">Обратите внимание, что типы данных `Byte`, `UShort`, `UInteger`, и `ULong` являются числа без знака, поэтому не знаковый бит для распространения.</span><span class="sxs-lookup"><span data-stu-id="46945-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="46945-123">Если `pattern` имеет любой без знака типа, освобождаемые всегда присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="46945-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="46945-124">Чтобы предотвратить сдвиг на количество битов, чем результат, Visual Basic маскирует значение `amount` с маской размер, соответствующий тип данных `pattern`.</span><span class="sxs-lookup"><span data-stu-id="46945-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="46945-125">Двоичное AND этих значений используется для сдвига.</span><span class="sxs-lookup"><span data-stu-id="46945-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="46945-126">Далее приведены маски размера.</span><span class="sxs-lookup"><span data-stu-id="46945-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="46945-127">Тип данных `pattern`</span><span class="sxs-lookup"><span data-stu-id="46945-127">Data type of `pattern`</span></span>|<span data-ttu-id="46945-128">Размер маски (десятичное)</span><span class="sxs-lookup"><span data-stu-id="46945-128">Size mask (decimal)</span></span>|<span data-ttu-id="46945-129">Размер маски (шестнадцатеричный)</span><span class="sxs-lookup"><span data-stu-id="46945-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="46945-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="46945-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="46945-131">7</span><span class="sxs-lookup"><span data-stu-id="46945-131">7</span></span>|<span data-ttu-id="46945-132">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="46945-132">&H00000007</span></span>|  
|<span data-ttu-id="46945-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="46945-133">`Short`, `UShort`</span></span>|<span data-ttu-id="46945-134">15</span><span class="sxs-lookup"><span data-stu-id="46945-134">15</span></span>|<span data-ttu-id="46945-135">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="46945-135">&H0000000F</span></span>|  
|<span data-ttu-id="46945-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="46945-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="46945-137">31</span><span class="sxs-lookup"><span data-stu-id="46945-137">31</span></span>|<span data-ttu-id="46945-138">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="46945-138">&H0000001F</span></span>|  
|<span data-ttu-id="46945-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="46945-139">`Long`, `ULong`</span></span>|<span data-ttu-id="46945-140">63</span><span class="sxs-lookup"><span data-stu-id="46945-140">63</span></span>|<span data-ttu-id="46945-141">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="46945-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="46945-142">Если `amount` равно нулю, значение `result` идентично значению `pattern`.</span><span class="sxs-lookup"><span data-stu-id="46945-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="46945-143">Если `amount` имеет отрицательное значение, он берется значение без знака и маскируется соответствующий размер маски.</span><span class="sxs-lookup"><span data-stu-id="46945-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="46945-144">Арифметические сдвиги никогда не создают исключения переполнения.</span><span class="sxs-lookup"><span data-stu-id="46945-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="46945-145">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="46945-145">Overloading</span></span>  
 <span data-ttu-id="46945-146">`>>` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="46945-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="46945-147">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="46945-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="46945-148">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="46945-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46945-149">Пример</span><span class="sxs-lookup"><span data-stu-id="46945-149">Example</span></span>  
 <span data-ttu-id="46945-150">В следующем примере используется `>>` оператор для выполнения арифметических при сдвиге вправо целых значений.</span><span class="sxs-lookup"><span data-stu-id="46945-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="46945-151">Результат всегда имеет тот же тип данных, выражения был перемещен.</span><span class="sxs-lookup"><span data-stu-id="46945-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="46945-152">Далее приведены результаты в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="46945-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="46945-153">`result1` является 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="46945-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="46945-154">`result2` равно 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="46945-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="46945-155">`result3` -2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="46945-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="46945-156">`result4` — 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="46945-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="46945-157">`result5` значение 0 (сдвигаются 15 разрядов справа).</span><span class="sxs-lookup"><span data-stu-id="46945-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="46945-158">Величина сдвига для `result4` вычисляется как 18 и 15, что соответствует 2.</span><span class="sxs-lookup"><span data-stu-id="46945-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="46945-159">В следующем примере показано арифметические сдвиги на отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="46945-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="46945-160">Далее приведены результаты в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="46945-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="46945-161">`negresult1` — -512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="46945-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="46945-162">`negresult2` -1 (распространяется знаковым битом).</span><span class="sxs-lookup"><span data-stu-id="46945-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46945-163">См. также</span><span class="sxs-lookup"><span data-stu-id="46945-163">See also</span></span>

- [<span data-ttu-id="46945-164">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="46945-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="46945-165">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="46945-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="46945-166">Оператор >>=</span><span class="sxs-lookup"><span data-stu-id="46945-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="46945-167">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46945-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="46945-168">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="46945-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="46945-169">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46945-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
