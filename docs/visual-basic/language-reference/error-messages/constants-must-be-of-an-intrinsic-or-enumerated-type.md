---
title: Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 702472751810c2d2bd08ece944ef0ffafc2049b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="e22a1-102">Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом</span><span class="sxs-lookup"><span data-stu-id="e22a1-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="e22a1-103">Предпринята попытка объявить константу как класса, структуры или тип массива, или как тип параметра, определенного типа содержащего универсального типа.</span><span class="sxs-lookup"><span data-stu-id="e22a1-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="e22a1-104">Константа должна быть встроенным типом (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, или `UShort`), или `Enum` типа на основе одного из целочисленных типов.</span><span class="sxs-lookup"><span data-stu-id="e22a1-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="e22a1-105">**Идентификатор ошибки:** BC30424</span><span class="sxs-lookup"><span data-stu-id="e22a1-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e22a1-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e22a1-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="e22a1-107">Объявите константу как встроенная функция или `Enum` типа.</span><span class="sxs-lookup"><span data-stu-id="e22a1-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="e22a1-108">Константы также может быть специальным значением например `True`, `False`, или `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e22a1-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="e22a1-109">Компилятор считает, что эти предопределенные значения соответствующего внутреннего типа.</span><span class="sxs-lookup"><span data-stu-id="e22a1-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22a1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e22a1-110">See Also</span></span>  
 [<span data-ttu-id="e22a1-111">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="e22a1-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="e22a1-112">Типы данных</span><span class="sxs-lookup"><span data-stu-id="e22a1-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e22a1-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="e22a1-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)
