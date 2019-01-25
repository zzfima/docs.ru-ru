---
title: '#Директива #const (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 7e855f76a0fa8e6c06fd557a944c518641415f09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710603"
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
 Обязательный. Литерал, другая константа условной компиляции или какое-либо сочетание включает любые или все арифметические или логические операторы, за исключением `Is`.  
  
## <a name="remarks"></a>Примечания  
 Константы условной компиляции всегда являются закрытыми для файла, в котором они появляются. Не удается создать открытые константы компилятора с помощью `#Const` директив; их можно создать только в пользовательском интерфейсе или с помощью `/define` параметр компилятора.  
  
 Можно использовать только константы условной компиляции и литералы в `expression`. Это стандартная константа, определенная с помощью `Const` приводит к ошибке. И наоборот, можно использовать константы, определенные с помощью `#Const` ключевое слово только для условной компиляции. Константы могут также быть неопределенными, в противном случае они имеют значение `Nothing`.  
  
## <a name="example"></a>Пример  
 В этом примере используется директива `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a>См. также
- [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
