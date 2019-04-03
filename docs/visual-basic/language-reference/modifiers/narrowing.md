---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838855"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="19f11-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19f11-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="19f11-103">Указывает, что оператор преобразования (`CType`) преобразует класс или структуру к типу, который не может содержать некоторые возможные значения исходного класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="19f11-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="19f11-104">Преобразования с сужением ключевым словом</span><span class="sxs-lookup"><span data-stu-id="19f11-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="19f11-105">Процедуры преобразования необходимо указать `Public Shared` в дополнение к `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="19f11-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="19f11-106">Сужающие преобразования не всегда успешного выполнения во время выполнения и может завершиться ошибкой или приводят к потере данных.</span><span class="sxs-lookup"><span data-stu-id="19f11-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="19f11-107">Примерами являются `Long` для `Integer`, `String` для `Date`и базового типа к производному типу.</span><span class="sxs-lookup"><span data-stu-id="19f11-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="19f11-108">Последнее преобразование является сужающим, поскольку базовый тип не может содержать все члены производного типа и таким образом не является экземпляром производного типа.</span><span class="sxs-lookup"><span data-stu-id="19f11-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="19f11-109">Если `Option Strict` — `On`, коду-потребителю необходимо использовать `CType` для всех сужающих преобразований.</span><span class="sxs-lookup"><span data-stu-id="19f11-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="19f11-110">`Narrowing` Слово может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="19f11-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="19f11-111">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="19f11-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="19f11-112">См. также</span><span class="sxs-lookup"><span data-stu-id="19f11-112">See also</span></span>

- [<span data-ttu-id="19f11-113">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="19f11-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="19f11-114">Расширение</span><span class="sxs-lookup"><span data-stu-id="19f11-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="19f11-115">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="19f11-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="19f11-116">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="19f11-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="19f11-117">Функция CType</span><span class="sxs-lookup"><span data-stu-id="19f11-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="19f11-118">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="19f11-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
