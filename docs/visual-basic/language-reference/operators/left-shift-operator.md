---
title: Оператор < < (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 1300ab60e825e7910825be2c65dcab90135ba988
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701114"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e2ffc-102">\<\<Оператор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2ffc-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="e2ffc-103">Выполняет арифметический сдвиг битового шаблона влево.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ffc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2ffc-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="e2ffc-105">Части</span><span class="sxs-lookup"><span data-stu-id="e2ffc-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e2ffc-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-106">Required.</span></span> <span data-ttu-id="e2ffc-107">Целое числовое значение.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-107">Integral numeric value.</span></span> <span data-ttu-id="e2ffc-108">Результат сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="e2ffc-109">Тип данных такой же, как `pattern`и у.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="e2ffc-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-110">Required.</span></span> <span data-ttu-id="e2ffc-111">Целое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-111">Integral numeric expression.</span></span> <span data-ttu-id="e2ffc-112">Битовый шаблон для сдвига.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="e2ffc-113">`SByte`Тип данных должен быть целочисленным типом ( `Byte` `Short`,,, `UShort` `UInteger` `Integer`,,, `Long`или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="e2ffc-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="e2ffc-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-114">Required.</span></span> <span data-ttu-id="e2ffc-115">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-115">Numeric expression.</span></span> <span data-ttu-id="e2ffc-116">Число битов для сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="e2ffc-117">Тип данных должен быть `Integer` или расширяться на. `Integer`</span><span class="sxs-lookup"><span data-stu-id="e2ffc-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2ffc-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2ffc-118">Remarks</span></span>  
 <span data-ttu-id="e2ffc-119">Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="e2ffc-120">При выполнении арифметического сдвига влево биты, сдвинутые за пределы диапазона результирующего типа данных, отбрасываются, а позиции битов, освобожденные справа, устанавливаются в ноль.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="e2ffc-121">Чтобы предотвратить сдвиг на больше бит, чем может вместить результат, Visual Basic маскирует значение `amount` с маской размера, соответствующей типу данных `pattern`.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="e2ffc-122">Двоичные значения и этих значений используются для величины сдвига.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="e2ffc-123">Ниже приведены маски размера.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="e2ffc-124">Тип данных `pattern`</span><span class="sxs-lookup"><span data-stu-id="e2ffc-124">Data type of `pattern`</span></span>|<span data-ttu-id="e2ffc-125">Маска размера (десятичная)</span><span class="sxs-lookup"><span data-stu-id="e2ffc-125">Size mask (decimal)</span></span>|<span data-ttu-id="e2ffc-126">Маска размера (шестнадцатеричная)</span><span class="sxs-lookup"><span data-stu-id="e2ffc-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="e2ffc-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="e2ffc-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="e2ffc-128">7</span><span class="sxs-lookup"><span data-stu-id="e2ffc-128">7</span></span>|<span data-ttu-id="e2ffc-129">& H00000007</span><span class="sxs-lookup"><span data-stu-id="e2ffc-129">&H00000007</span></span>|  
|<span data-ttu-id="e2ffc-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="e2ffc-130">`Short`, `UShort`</span></span>|<span data-ttu-id="e2ffc-131">15</span><span class="sxs-lookup"><span data-stu-id="e2ffc-131">15</span></span>|<span data-ttu-id="e2ffc-132">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="e2ffc-132">&H0000000F</span></span>|  
|<span data-ttu-id="e2ffc-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="e2ffc-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="e2ffc-134">31</span><span class="sxs-lookup"><span data-stu-id="e2ffc-134">31</span></span>|<span data-ttu-id="e2ffc-135">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="e2ffc-135">&H0000001F</span></span>|  
|<span data-ttu-id="e2ffc-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="e2ffc-136">`Long`, `ULong`</span></span>|<span data-ttu-id="e2ffc-137">63</span><span class="sxs-lookup"><span data-stu-id="e2ffc-137">63</span></span>|<span data-ttu-id="e2ffc-138">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="e2ffc-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="e2ffc-139">Если `amount` равно нулю, значение `result` идентично значению `pattern`.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="e2ffc-140">Если `amount` является отрицательным, он принимается как значение без знака и маскируется с соответствующей маской размера.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="e2ffc-141">Арифметические сдвиги никогда не создают исключений переполнения.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2ffc-142">Оператор `<<` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e2ffc-143">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="e2ffc-144">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e2ffc-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2ffc-145">Пример</span><span class="sxs-lookup"><span data-stu-id="e2ffc-145">Example</span></span>  
 <span data-ttu-id="e2ffc-146">В следующем примере оператор `<<` используется для выполнения арифметических сдвигов влево по целочисленным значениям.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="e2ffc-147">Результат всегда имеет тот же тип данных, что и выражение, для которого выполняется сдвиг.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="e2ffc-148">Результаты предыдущего примера выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2ffc-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="e2ffc-149">`result1` — 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="e2ffc-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="e2ffc-150">`result2` — 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="e2ffc-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="e2ffc-151">`result3` — 32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="e2ffc-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="e2ffc-152">`result4` — 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="e2ffc-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="e2ffc-153">`result5` равно 0 (смещено 15 позиций влево).</span><span class="sxs-lookup"><span data-stu-id="e2ffc-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="e2ffc-154">Сумма сдвига для `result4` вычисляется как 17 и 15, что равно 1.</span><span class="sxs-lookup"><span data-stu-id="e2ffc-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ffc-155">См. также</span><span class="sxs-lookup"><span data-stu-id="e2ffc-155">See also</span></span>

- [<span data-ttu-id="e2ffc-156">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="e2ffc-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="e2ffc-157">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="e2ffc-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="e2ffc-158">Оператор <<=</span><span class="sxs-lookup"><span data-stu-id="e2ffc-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="e2ffc-159">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2ffc-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e2ffc-160">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="e2ffc-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e2ffc-161">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2ffc-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
