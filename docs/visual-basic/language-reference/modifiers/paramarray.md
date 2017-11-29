---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Указывает, что параметр процедуры принимает необязательный массив элементов заданного типа. `ParamArray`может использоваться только для последнего параметра из списка параметров.  
  
## <a name="remarks"></a>Примечания  
 `ParamArray`позволяет передать произвольное число аргументов в процедуру. Объект `ParamArray` всегда параметр объявлен с помощью [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 Можно указать один или несколько аргументов для `ParamArray` параметра при передаче массива соответствующие данные типа, список разделенных запятыми значений или nothing вообще. Дополнительные сведения см. в разделе «Вызов ParamArray» в [массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  При работе с которой неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения. Если вы принимаете массив параметров из вызывающего кода, следует проверить его длину и предпринять соответствующие действия, если она слишком велика для приложения.  
  
 Модификатор `ParamArray` можно использовать в следующих контекстах:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
