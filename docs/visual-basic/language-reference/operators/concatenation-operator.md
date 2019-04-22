---
title: '&amp; Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: dd85363447e9b405241d608550d9484b4760a739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817283"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="0bdb1-102">&amp; Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bdb1-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="0bdb1-103">Приводит к возникновению ошибки объединения строк из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bdb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bdb1-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="0bdb1-105">Части</span><span class="sxs-lookup"><span data-stu-id="0bdb1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="0bdb1-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-106">Required.</span></span> <span data-ttu-id="0bdb1-107">Любой `String` или `Object` переменной.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="0bdb1-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-108">Required.</span></span> <span data-ttu-id="0bdb1-109">Любое выражение с типом данных, который расширяется до `String`.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="0bdb1-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-110">Required.</span></span> <span data-ttu-id="0bdb1-111">Любое выражение с типом данных, который расширяется до `String`.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bdb1-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bdb1-112">Remarks</span></span>  
 <span data-ttu-id="0bdb1-113">Если тип данных `expression1` или `expression2` не `String` , но можно расширить до `String`, он преобразуется в `String`.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="0bdb1-114">Если один из типов данных не расширяется до `String`, компилятор выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="0bdb1-115">Тип данных `result` является `String`.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="0bdb1-116">Если один или оба выражения [ничего не](../../../visual-basic/language-reference/nothing.md) или иметь значение <xref:System.DBNull.Value?displayProperty=nameWithType>, они обрабатываются как строки со значением «».</span><span class="sxs-lookup"><span data-stu-id="0bdb1-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bdb1-117">`&` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0bdb1-118">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0bdb1-119">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0bdb1-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bdb1-120">Символ амперсанда (&) может также использоваться для определения переменных, как тип `Long`.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="0bdb1-121">Дополнительные сведения см. в разделе [символы типа](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="0bdb1-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bdb1-122">Пример</span><span class="sxs-lookup"><span data-stu-id="0bdb1-122">Example</span></span>  
 <span data-ttu-id="0bdb1-123">В этом примере используется `&` оператор для принудительного объединения строк.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="0bdb1-124">Результатом является строковое значение, представляющее объединение двух строковых операндов.</span><span class="sxs-lookup"><span data-stu-id="0bdb1-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0bdb1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0bdb1-125">See also</span></span>

- [<span data-ttu-id="0bdb1-126">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="0bdb1-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="0bdb1-127">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="0bdb1-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="0bdb1-128">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0bdb1-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="0bdb1-129">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="0bdb1-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="0bdb1-130">Операторы объединения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0bdb1-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
