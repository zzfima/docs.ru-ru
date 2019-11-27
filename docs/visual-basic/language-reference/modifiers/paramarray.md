---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: fbc87bffebc265e6062512e96fc29a64334b3c65
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351374"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Указывает, что параметр процедуры принимает необязательный массив элементов указанного типа. `ParamArray` можно использовать только в последнем параметре списка параметров.  
  
## <a name="remarks"></a>Примечания  
 `ParamArray` позволяет передавать в процедуру произвольное число аргументов. Параметр `ParamArray` всегда объявляется с помощью [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 Можно указать один или несколько аргументов для параметра `ParamArray`, передав массив соответствующего типа данных, список значений с разделителями-запятыми или ничего вообще. Дополнительные сведения см. в разделе «вызов ParamArray» в [массивах параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Всякий раз при работе с массивом, который может быть неограниченным большим, существует риск перегрузки внутренней емкости приложения. Если вы принимаете массив параметров из вызывающего кода, следует проверить его длину и предпринять соответствующие шаги, если оно слишком велико для вашего приложения.  
  
 Модификатор `ParamArray` можно использовать в следующих контекстах:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
