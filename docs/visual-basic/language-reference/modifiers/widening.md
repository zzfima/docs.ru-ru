---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: d7d43d4f5f931881d5c8b663c719fe7f92559799
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825317"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="4a46d-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a46d-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="4a46d-103">Указывает, что оператор преобразования (`CType`) преобразует класс или структуру к типу, который может содержать все возможные значения исходного класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4a46d-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="4a46d-104">С помощью ключевого слова расширяющее преобразование</span><span class="sxs-lookup"><span data-stu-id="4a46d-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="4a46d-105">Процедуры преобразования необходимо указать `Public Shared` в дополнение к `Widening`.</span><span class="sxs-lookup"><span data-stu-id="4a46d-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="4a46d-106">Расширяющие преобразования всегда успешно обрабатываются во время выполнения и никогда не приводят к потере данных.</span><span class="sxs-lookup"><span data-stu-id="4a46d-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="4a46d-107">Примерами являются `Single` для `Double`, `Char` для `String`и производный тип к его базовому типу.</span><span class="sxs-lookup"><span data-stu-id="4a46d-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="4a46d-108">Последнее преобразование является расширяющим, так как производный тип содержит все члены базового типа и таким образом — это экземпляр базового типа.</span><span class="sxs-lookup"><span data-stu-id="4a46d-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="4a46d-109">Не использовать код-потребитель `CType` для расширяющих преобразований, даже если `Option Strict` является `On`.</span><span class="sxs-lookup"><span data-stu-id="4a46d-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="4a46d-110">`Widening` Слово может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="4a46d-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="4a46d-111">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="4a46d-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="4a46d-112">Пример определения расширяющие и сужающие преобразования операторов, см. в разделе [как: Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4a46d-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a46d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4a46d-113">See also</span></span>

- [<span data-ttu-id="4a46d-114">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="4a46d-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="4a46d-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="4a46d-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="4a46d-116">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="4a46d-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="4a46d-117">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="4a46d-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="4a46d-118">Функция CType</span><span class="sxs-lookup"><span data-stu-id="4a46d-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="4a46d-119">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="4a46d-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="4a46d-120">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="4a46d-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
