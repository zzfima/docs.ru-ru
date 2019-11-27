---
title: Оператор &amp;
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
ms.openlocfilehash: 4cae7e59083890e82d754bdaa58942c2224357b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336060"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="1996c-102">Оператор &amp; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1996c-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="1996c-103">Формирует объединение строк двух выражений.</span><span class="sxs-lookup"><span data-stu-id="1996c-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1996c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1996c-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="1996c-105">Части</span><span class="sxs-lookup"><span data-stu-id="1996c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="1996c-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="1996c-106">Required.</span></span> <span data-ttu-id="1996c-107">Любая `String` или `Object`ая переменная.</span><span class="sxs-lookup"><span data-stu-id="1996c-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="1996c-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="1996c-108">Required.</span></span> <span data-ttu-id="1996c-109">Любое выражение с типом данных, которое расширяется до `String`.</span><span class="sxs-lookup"><span data-stu-id="1996c-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="1996c-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="1996c-110">Required.</span></span> <span data-ttu-id="1996c-111">Любое выражение с типом данных, которое расширяется до `String`.</span><span class="sxs-lookup"><span data-stu-id="1996c-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1996c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="1996c-112">Remarks</span></span>  
 <span data-ttu-id="1996c-113">Если тип данных `expression1` или `expression2` не `String`, но расширяется до `String`, он преобразуется в `String`.</span><span class="sxs-lookup"><span data-stu-id="1996c-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="1996c-114">Если любой из типов данных не расширяется до `String`, компилятор выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="1996c-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="1996c-115">Тип данных `result` `String`.</span><span class="sxs-lookup"><span data-stu-id="1996c-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="1996c-116">Если одно или оба выражения имеют значение [Nothing](../../../visual-basic/language-reference/nothing.md) или не имеют значения <xref:System.DBNull.Value?displayProperty=nameWithType>, они обрабатываются как строка со значением "".</span><span class="sxs-lookup"><span data-stu-id="1996c-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1996c-117">Оператор `&` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="1996c-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1996c-118">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="1996c-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1996c-119">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1996c-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1996c-120">Символ амперсанда (&) также можно использовать для задания переменных как типа `Long`.</span><span class="sxs-lookup"><span data-stu-id="1996c-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="1996c-121">Дополнительные сведения см. в разделе [символы типа](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="1996c-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1996c-122">Пример</span><span class="sxs-lookup"><span data-stu-id="1996c-122">Example</span></span>  
 <span data-ttu-id="1996c-123">В этом примере оператор `&` используется для принудительного сцепления строк.</span><span class="sxs-lookup"><span data-stu-id="1996c-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="1996c-124">Результатом является строковое значение, представляющее объединение двух строковых операндов.</span><span class="sxs-lookup"><span data-stu-id="1996c-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1996c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1996c-125">See also</span></span>

- [<span data-ttu-id="1996c-126">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="1996c-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="1996c-127">Операторы объединения</span><span class="sxs-lookup"><span data-stu-id="1996c-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="1996c-128">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1996c-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1996c-129">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="1996c-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1996c-130">Операторы объединения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1996c-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
