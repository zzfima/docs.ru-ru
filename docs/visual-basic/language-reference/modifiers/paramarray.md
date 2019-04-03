---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: b9dee0fc876c6e7a02d085db7db4bf1c5dd2c68d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816669"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Указывает, что параметр процедуры принимает необязательный массив элементов указанного типа. `ParamArray` может использоваться только для последнего параметра в списке параметров.  
  
## <a name="remarks"></a>Примечания  
 `ParamArray` позволяет передать произвольное число аргументов в процедуру. Объект `ParamArray` параметр всегда объявляется с помощью [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 Можно указать один или несколько аргументов для `ParamArray` при передаче массива данных, соответствующий тип параметра, разделенный запятыми список значений, либо значение nothing вообще. Дополнительные сведения см. в разделе «Вызов ParamArray» в [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  Каждый раз, когда вы имеете дело с массив, который может быть неограниченно большим, есть риск переполнения некоторой внутренней емкости приложения. Если вы согласны с массивом параметров от вызывающего кода, следует проверить его длину и предпринять соответствующие действия, если она слишком велика для приложения.  
  
 Модификатор `ParamArray` можно использовать в следующих контекстах:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
