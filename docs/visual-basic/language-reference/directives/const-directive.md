---
title: '#Директива Const (Visual Basic)'
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
ms.openlocfilehash: 9b8d2da2158a8244b4533eb6ef49049949417216
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696857"
---
# <a name="const-directive"></a>Директива #Const
Определяет константы условной компилятора для Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Части  
 `constname`  
 Обязательный. Имя определяемой константы.  
  
 `expression`  
 Обязательный. Литерал, другая условная константа компилятора или любое сочетание, включающее любые или все арифметические или логические операторы, кроме `Is`.  
  
## <a name="remarks"></a>Примечания  
 Константы условной компиляции всегда являются частными для файла, в котором они отображаются. Нельзя создавать открытые константы компилятора с помощью директивы `#Const`; их можно создавать только в пользовательском интерфейсе или с параметром компилятора `/define`.  
  
 В `expression` можно использовать только константы условной компиляции и литералы. Использование стандартной константы, определенной с `Const`, приводит к ошибке. И наоборот, константы, определенные с помощью ключевого слова `#Const`, можно использовать только для условной компиляции. Константы также могут быть неопределенными, в этом случае они имеют значение `Nothing`.  
  
## <a name="example"></a>Пример  
 В этом примере используется директива `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
