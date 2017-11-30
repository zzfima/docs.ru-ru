---
title: "#<a name=\"const-directive\"></a>Директива #const"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="const-directive"></a>Директива #Const
Задает константы условной компиляции для Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Части  
 `constname`  
 Обязательный. Имя определяемой константы.  
  
 `expression`  
 Обязательный. Литерал, другая константа условной компиляции или любой их комбинацией, включающей любые или все арифметические или логические операторы, за исключением `Is`.  
  
## <a name="remarks"></a>Примечания  
 Константы условной компиляции всегда являются закрытыми для файла, в котором они отображаются. Не удается создать открытые константы условной компиляции с помощью `#Const` директив; их можно создать только в пользовательском интерфейсе или с `/define` параметр компилятора.  
  
 Можно использовать только константы условной компиляции и литералы в `expression`. С помощью стандартных констант в определении `Const` приводит к ошибке. И наоборот, можно использовать константы, определенные с `#Const` ключевое слово только для условной компиляции. Константы могут также быть неопределенными, при этом они имеют значение `Nothing`.  
  
## <a name="example"></a>Пример  
 В этом примере используется директива `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
