---
title: Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 9039376fc4d1f67ca9b526e46eaf28a0b1a3943c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587486"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
Предпринята попытка объявить константу как класса, структуры или тип массива, или как тип параметра, определенного типа содержащего универсального типа.  
  
 Константа должна быть встроенным типом (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, или `UShort`), или `Enum` типа на основе одного из целочисленных типов.  
  
 **Идентификатор ошибки:** BC30424  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите константу как встроенная функция или `Enum` типа.  
  
2.  Константы также может быть специальным значением например `True`, `False`, или `Nothing`. Компилятор считает, что эти предопределенные значения соответствующего внутреннего типа.  
  
## <a name="see-also"></a>См. также  
 [Константы и перечисления](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Типы данных](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)
