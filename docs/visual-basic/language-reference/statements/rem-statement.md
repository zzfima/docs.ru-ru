---
title: Оператор REM (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 16149ce42e3476cf07a62298f83734fee9ec7253
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957763"
---
# <a name="rem-statement-visual-basic"></a>Оператор REM (Visual Basic)
Используется для включения пояснительных примечаний в исходный код программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Части  
 `comment`  
 Необязательный параметр. Текст любого комментария, который требуется включить. Между `REM` ключевым словом и `comment`должен быть пробел.  
  
## <a name="remarks"></a>Примечания  
 `REM` Оператор можно разместить только в строке или вставить в строку, следующую за другой инструкцией. `REM` Оператор должен быть последним оператором в строке. Если он соответствует другому оператору, `REM` он должен быть отделен от этого оператора пробелом.  
  
 Можно использовать одиночную кавычку (`'`) `REM`вместо. Это верно, если ваш комментарий следует другому оператору в той же строке или расподержаться только в строке.  
  
> [!NOTE]
> Нельзя продолжить выполнение `REM` инструкции с помощью последовательности продолжения строки (`_`). После начала комментария компилятор не проверяет символы на предмет особого значения. Для многострочного комментария используйте другую `REM` инструкцию или символ комментария (`'`) в каждой строке.  
  
## <a name="example"></a>Пример  
 В следующем примере показана `REM` инструкция, которая используется для включения пояснительных примечаний в программу. Он также показывает альтернативу использованию символа одинарной кавычки (`'`) `REM`вместо.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Комментарии в коде](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
