---
title: Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 0f4cb04558bf9768de22f432a1c59203643aba6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595847"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="406a3-102">Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом</span><span class="sxs-lookup"><span data-stu-id="406a3-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="406a3-103">Предпринята попытка объявить константу, класса, структуры или тип массива или тип параметра, определенного содержащего универсального типа.</span><span class="sxs-lookup"><span data-stu-id="406a3-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="406a3-104">Константы должны быть значениями встроенного типа (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, или `UShort`), или `Enum` тип на основе одного из целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="406a3-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="406a3-105">**Идентификатор ошибки:** BC30424</span><span class="sxs-lookup"><span data-stu-id="406a3-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="406a3-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="406a3-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="406a3-107">Объявите константу как встроенная или `Enum` типа.</span><span class="sxs-lookup"><span data-stu-id="406a3-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="406a3-108">Константа также может быть специальное значение например `True`, `False`, или `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="406a3-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="406a3-109">Компилятор считает, что эти предопределенные значения соответствующего внутреннего типа.</span><span class="sxs-lookup"><span data-stu-id="406a3-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406a3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="406a3-110">See also</span></span>
- [<span data-ttu-id="406a3-111">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="406a3-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="406a3-112">Типы данных</span><span class="sxs-lookup"><span data-stu-id="406a3-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="406a3-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="406a3-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
