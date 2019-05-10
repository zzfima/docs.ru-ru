---
title: << Оператора (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: e11dbc453934f1aac4a8092cdc6539ec11f0cc21
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663183"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="82f11-102">\<\< Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82f11-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="82f11-103">Выполняет арифметическое смещение влево битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="82f11-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82f11-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="82f11-105">Части</span><span class="sxs-lookup"><span data-stu-id="82f11-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="82f11-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="82f11-106">Required.</span></span> <span data-ttu-id="82f11-107">Целое числовое значение.</span><span class="sxs-lookup"><span data-stu-id="82f11-107">Integral numeric value.</span></span> <span data-ttu-id="82f11-108">Результат сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="82f11-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="82f11-109">Тип данных является таким же, как `pattern`.</span><span class="sxs-lookup"><span data-stu-id="82f11-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="82f11-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="82f11-110">Required.</span></span> <span data-ttu-id="82f11-111">Целое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="82f11-111">Integral numeric expression.</span></span> <span data-ttu-id="82f11-112">Битовый шаблон должны сдвигаться.</span><span class="sxs-lookup"><span data-stu-id="82f11-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="82f11-113">Тип данных должен быть целочисленный тип (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).</span><span class="sxs-lookup"><span data-stu-id="82f11-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="82f11-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="82f11-114">Required.</span></span> <span data-ttu-id="82f11-115">Числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="82f11-115">Numeric expression.</span></span> <span data-ttu-id="82f11-116">Количество битов для сдвига битового шаблона.</span><span class="sxs-lookup"><span data-stu-id="82f11-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="82f11-117">Тип данных должен быть `Integer` или расширяющего преобразования к `Integer`.</span><span class="sxs-lookup"><span data-stu-id="82f11-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82f11-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="82f11-118">Remarks</span></span>  
 <span data-ttu-id="82f11-119">Арифметические сдвиги не являются циклическими, это означает, что биты, сдвигаемые результата, не подставляются на другом конце.</span><span class="sxs-lookup"><span data-stu-id="82f11-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="82f11-120">В арифметического сдвига влево биты, перемещен за пределы диапазона для типа данных результата отбрасываются и освободившиеся справа позиции битов заполняются нулями.</span><span class="sxs-lookup"><span data-stu-id="82f11-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="82f11-121">Чтобы предотвратить сдвиг на количество битов, превышающее битов результата, Visual Basic маскирует значение `amount` с маской размер, соответствующий тип данных `pattern`.</span><span class="sxs-lookup"><span data-stu-id="82f11-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="82f11-122">Двоичное AND этих значений используется для сдвига.</span><span class="sxs-lookup"><span data-stu-id="82f11-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="82f11-123">Далее приведены маски размера.</span><span class="sxs-lookup"><span data-stu-id="82f11-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="82f11-124">Тип данных `pattern`</span><span class="sxs-lookup"><span data-stu-id="82f11-124">Data type of `pattern`</span></span>|<span data-ttu-id="82f11-125">Размер маски (десятичное)</span><span class="sxs-lookup"><span data-stu-id="82f11-125">Size mask (decimal)</span></span>|<span data-ttu-id="82f11-126">Размер маски (шестнадцатеричный)</span><span class="sxs-lookup"><span data-stu-id="82f11-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="82f11-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="82f11-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="82f11-128">7</span><span class="sxs-lookup"><span data-stu-id="82f11-128">7</span></span>|<span data-ttu-id="82f11-129">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="82f11-129">&H00000007</span></span>|  
|<span data-ttu-id="82f11-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="82f11-130">`Short`, `UShort`</span></span>|<span data-ttu-id="82f11-131">15</span><span class="sxs-lookup"><span data-stu-id="82f11-131">15</span></span>|<span data-ttu-id="82f11-132">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="82f11-132">&H0000000F</span></span>|  
|<span data-ttu-id="82f11-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="82f11-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="82f11-134">31</span><span class="sxs-lookup"><span data-stu-id="82f11-134">31</span></span>|<span data-ttu-id="82f11-135">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="82f11-135">&H0000001F</span></span>|  
|<span data-ttu-id="82f11-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="82f11-136">`Long`, `ULong`</span></span>|<span data-ttu-id="82f11-137">63</span><span class="sxs-lookup"><span data-stu-id="82f11-137">63</span></span>|<span data-ttu-id="82f11-138">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="82f11-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="82f11-139">Если `amount` равно нулю, значение `result` идентично значению `pattern`.</span><span class="sxs-lookup"><span data-stu-id="82f11-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="82f11-140">Если `amount` имеет отрицательное значение, он берется значение без знака и маскируется соответствующий размер маски.</span><span class="sxs-lookup"><span data-stu-id="82f11-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="82f11-141">Арифметические сдвиги никогда не создают исключения переполнения.</span><span class="sxs-lookup"><span data-stu-id="82f11-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82f11-142">`<<` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="82f11-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="82f11-143">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что переопределенное его.</span><span class="sxs-lookup"><span data-stu-id="82f11-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="82f11-144">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="82f11-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82f11-145">Пример</span><span class="sxs-lookup"><span data-stu-id="82f11-145">Example</span></span>  
 <span data-ttu-id="82f11-146">В следующем примере используется `<<` оператор для выполнения арифметических левых сдвигов целых значений.</span><span class="sxs-lookup"><span data-stu-id="82f11-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="82f11-147">Результат всегда имеет тот же тип данных, выражения был перемещен.</span><span class="sxs-lookup"><span data-stu-id="82f11-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="82f11-148">Далее приведены результаты предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="82f11-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="82f11-149">`result1` — 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="82f11-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="82f11-150">`result2` равен 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="82f11-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="82f11-151">`result3` — от -32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="82f11-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="82f11-152">`result4` — 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="82f11-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="82f11-153">`result5` значение 0 (сдвигаются 15 разрядами слева).</span><span class="sxs-lookup"><span data-stu-id="82f11-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="82f11-154">Величина сдвига для `result4` вычисляется как 17 и 15, что равно 1.</span><span class="sxs-lookup"><span data-stu-id="82f11-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f11-155">См. также</span><span class="sxs-lookup"><span data-stu-id="82f11-155">See also</span></span>

- [<span data-ttu-id="82f11-156">Операторы сдвига битов</span><span class="sxs-lookup"><span data-stu-id="82f11-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="82f11-157">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="82f11-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="82f11-158">Оператор <<=</span><span class="sxs-lookup"><span data-stu-id="82f11-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="82f11-159">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82f11-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="82f11-160">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="82f11-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="82f11-161">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82f11-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
