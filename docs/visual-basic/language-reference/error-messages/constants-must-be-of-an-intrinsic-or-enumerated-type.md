---
title: Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 88bbab2005b464ee97d647f2b4b9be6ff81e2d82
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299115"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
Предпринята попытка объявить константу, класса, структуры или тип массива или тип параметра, определенного содержащего универсального типа.  
  
 Константы должны быть значениями встроенного типа (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, или `UShort`), или `Enum` тип на основе одного из целочисленных типов.  
  
 **Идентификатор ошибки:** BC30424  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Объявите константу как встроенная или `Enum` типа.  
  
2. Константа также может быть специальное значение например `True`, `False`, или `Nothing`. Компилятор считает, что эти предопределенные значения соответствующего внутреннего типа.  
  
## <a name="see-also"></a>См. также

- [Константы и перечисления](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Типы данных](../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
