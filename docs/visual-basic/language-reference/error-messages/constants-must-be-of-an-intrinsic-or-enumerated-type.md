---
title: Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 4d635d289ed99aed48c296c278bc546971af51da
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999205"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="b74f2-102">Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом</span><span class="sxs-lookup"><span data-stu-id="b74f2-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="b74f2-103">Предпринята попытка объявить константу, класса, структуры или тип массива или тип параметра, определенного содержащего универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b74f2-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="b74f2-104">Константы должны быть значениями встроенного типа (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, или `UShort`), или `Enum` тип на основе одного из целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="b74f2-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="b74f2-105">**Идентификатор ошибки:** BC30424</span><span class="sxs-lookup"><span data-stu-id="b74f2-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b74f2-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b74f2-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b74f2-107">Объявите константу как встроенная или `Enum` типа.</span><span class="sxs-lookup"><span data-stu-id="b74f2-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="b74f2-108">Константа также может быть специальное значение например `True`, `False`, или `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b74f2-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="b74f2-109">Компилятор считает, что эти предопределенные значения соответствующего внутреннего типа.</span><span class="sxs-lookup"><span data-stu-id="b74f2-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74f2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b74f2-110">See Also</span></span>  
 [<span data-ttu-id="b74f2-111">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="b74f2-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="b74f2-112">Типы данных</span><span class="sxs-lookup"><span data-stu-id="b74f2-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="b74f2-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="b74f2-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
