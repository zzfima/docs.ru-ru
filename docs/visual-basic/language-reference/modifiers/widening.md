---
title: Widening
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
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347833"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="0f350-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f350-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="0f350-103">Указывает, что оператор преобразования (`CType`) преобразует класс или структуру в тип, который может содержать все возможные значения исходного класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="0f350-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="0f350-104">Преобразование с помощью ключевого слова Widening</span><span class="sxs-lookup"><span data-stu-id="0f350-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="0f350-105">В дополнение к `Widening`у в процедуре преобразования необходимо указать `Public Shared`.</span><span class="sxs-lookup"><span data-stu-id="0f350-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="0f350-106">Расширяющие преобразования всегда выполняются в период выполнения и никогда не вызывают потери данных.</span><span class="sxs-lookup"><span data-stu-id="0f350-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="0f350-107">Примеры `Single` для `Double`, `Char` `String`и производного типа к его базовому типу.</span><span class="sxs-lookup"><span data-stu-id="0f350-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="0f350-108">Последнее преобразование является расширяющим, так как производный тип содержит все члены базового типа и, таким же, является экземпляром базового типа.</span><span class="sxs-lookup"><span data-stu-id="0f350-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="0f350-109">В таком коде не обязательно использовать `CType` для расширяющего преобразования, даже если `Option Strict` `On`.</span><span class="sxs-lookup"><span data-stu-id="0f350-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="0f350-110">В этом контексте можно использовать ключевое слово `Widening`:</span><span class="sxs-lookup"><span data-stu-id="0f350-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="0f350-111">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="0f350-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="0f350-112">Примеры определений расширяющих и суженных операторов преобразования см. в разделе [руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0f350-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f350-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0f350-113">See also</span></span>

- [<span data-ttu-id="0f350-114">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="0f350-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="0f350-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="0f350-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="0f350-116">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="0f350-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="0f350-117">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="0f350-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="0f350-118">CType Function</span><span class="sxs-lookup"><span data-stu-id="0f350-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="0f350-119">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="0f350-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="0f350-120">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="0f350-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
