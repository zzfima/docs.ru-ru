---
title: Оператор <<
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 327d0e5cbd1ebcc43bd47fb068f4513940c2165a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350986"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="20be3-102">Оператор \<\< (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20be3-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="20be3-103">Выполняет арифметический сдвиг битового шаблона влево.</span><span class="sxs-lookup"><span data-stu-id="20be3-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20be3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20be3-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="20be3-105">Части</span><span class="sxs-lookup"><span data-stu-id="20be3-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="20be3-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="20be3-106">Required.</span></span> <span data-ttu-id="20be3-107">Целое числовое значение.</span><span class="sxs-lookup"><span data-stu-id="20be3-107">Integral numeric value.</span></span> <span data-ttu-id="20be3-108">Результат сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="20be3-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="20be3-109">Тип данных совпадает с типом `pattern`.</span><span class="sxs-lookup"><span data-stu-id="20be3-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="20be3-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="20be3-110">Required.</span></span> <span data-ttu-id="20be3-111">Целое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="20be3-111">Integral numeric expression.</span></span> <span data-ttu-id="20be3-112">Битовый шаблон для сдвига.</span><span class="sxs-lookup"><span data-stu-id="20be3-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="20be3-113">Тип данных должен быть целочисленным типом (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="20be3-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="20be3-114">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="20be3-114">Required.</span></span> <span data-ttu-id="20be3-115">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="20be3-115">Numeric expression.</span></span> <span data-ttu-id="20be3-116">Число битов для сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="20be3-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="20be3-117">Для `Integer`тип данных должен быть `Integer` или расширяться.</span><span class="sxs-lookup"><span data-stu-id="20be3-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20be3-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="20be3-118">Remarks</span></span>  
 <span data-ttu-id="20be3-119">Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец.</span><span class="sxs-lookup"><span data-stu-id="20be3-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="20be3-120">При выполнении арифметического сдвига влево биты, сдвинутые за пределы диапазона результирующего типа данных, отбрасываются, а позиции битов, освобожденные справа, устанавливаются в ноль.</span><span class="sxs-lookup"><span data-stu-id="20be3-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="20be3-121">Чтобы предотвратить сдвиг на большее количество битов, чем может вместить результат, Visual Basic маскирует значение `amount` с маской размера, соответствующей типу данных `pattern`.</span><span class="sxs-lookup"><span data-stu-id="20be3-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="20be3-122">Двоичные значения и этих значений используются для величины сдвига.</span><span class="sxs-lookup"><span data-stu-id="20be3-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="20be3-123">Ниже приведены маски размера.</span><span class="sxs-lookup"><span data-stu-id="20be3-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="20be3-124">Тип данных `pattern`</span><span class="sxs-lookup"><span data-stu-id="20be3-124">Data type of `pattern`</span></span>|<span data-ttu-id="20be3-125">Маска размера (десятичная)</span><span class="sxs-lookup"><span data-stu-id="20be3-125">Size mask (decimal)</span></span>|<span data-ttu-id="20be3-126">Маска размера (шестнадцатеричная)</span><span class="sxs-lookup"><span data-stu-id="20be3-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="20be3-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="20be3-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="20be3-128">7</span><span class="sxs-lookup"><span data-stu-id="20be3-128">7</span></span>|<span data-ttu-id="20be3-129">& H00000007</span><span class="sxs-lookup"><span data-stu-id="20be3-129">&H00000007</span></span>|  
|<span data-ttu-id="20be3-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="20be3-130">`Short`, `UShort`</span></span>|<span data-ttu-id="20be3-131">15</span><span class="sxs-lookup"><span data-stu-id="20be3-131">15</span></span>|<span data-ttu-id="20be3-132">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="20be3-132">&H0000000F</span></span>|  
|<span data-ttu-id="20be3-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="20be3-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="20be3-134">31</span><span class="sxs-lookup"><span data-stu-id="20be3-134">31</span></span>|<span data-ttu-id="20be3-135">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="20be3-135">&H0000001F</span></span>|  
|<span data-ttu-id="20be3-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="20be3-136">`Long`, `ULong`</span></span>|<span data-ttu-id="20be3-137">63</span><span class="sxs-lookup"><span data-stu-id="20be3-137">63</span></span>|<span data-ttu-id="20be3-138">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="20be3-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="20be3-139">Если `amount` равен нулю, значение `result` идентично значению `pattern`.</span><span class="sxs-lookup"><span data-stu-id="20be3-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="20be3-140">Если `amount` является отрицательным, он принимается как значение без знака и маскируется с соответствующей маской размера.</span><span class="sxs-lookup"><span data-stu-id="20be3-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="20be3-141">Арифметические сдвиги никогда не создают исключений переполнения.</span><span class="sxs-lookup"><span data-stu-id="20be3-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20be3-142">Оператор `<<` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="20be3-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="20be3-143">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="20be3-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="20be3-144">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="20be3-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20be3-145">Пример</span><span class="sxs-lookup"><span data-stu-id="20be3-145">Example</span></span>  
 <span data-ttu-id="20be3-146">В следующем примере оператор `<<` используется для выполнения арифметических сдвигов влево по целочисленным значениям.</span><span class="sxs-lookup"><span data-stu-id="20be3-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="20be3-147">Результат всегда имеет тот же тип данных, что и выражение, для которого выполняется сдвиг.</span><span class="sxs-lookup"><span data-stu-id="20be3-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="20be3-148">Результаты предыдущего примера выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="20be3-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="20be3-149">`result1` — 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="20be3-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="20be3-150">`result2` — 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="20be3-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="20be3-151">`result3` — 32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="20be3-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="20be3-152">`result4` — 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="20be3-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="20be3-153">`result5` равен 0 (смещено 15 позиций влево).</span><span class="sxs-lookup"><span data-stu-id="20be3-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="20be3-154">Сумма сдвига для `result4` вычисляется как 17 и 15, что равно 1.</span><span class="sxs-lookup"><span data-stu-id="20be3-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20be3-155">См. также</span><span class="sxs-lookup"><span data-stu-id="20be3-155">See also</span></span>

- [<span data-ttu-id="20be3-156">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="20be3-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="20be3-157">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="20be3-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="20be3-158">Оператор <<=</span><span class="sxs-lookup"><span data-stu-id="20be3-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="20be3-159">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20be3-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="20be3-160">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="20be3-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="20be3-161">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20be3-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
