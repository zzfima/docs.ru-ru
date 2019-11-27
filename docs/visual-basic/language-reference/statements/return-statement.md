---
title: Оператор Return
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333016"
---
# <a name="return-statement-visual-basic"></a>Оператор Return (Visual Basic)
Возвращает управление коду, который вызвал процедуру `Function`, `Sub`, `Get`, `Set`или `Operator`.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Отделение  
 `expression`  
 Требуется в `Function`, `Get`или процедуре `Operator`. Выражение, представляющее значение, возвращаемое вызывающему коду.  
  
## <a name="remarks"></a>Примечания  
 В `Sub` или `Set` инструкция `Return` эквивалентна инструкции `Exit Sub` или `Exit Property`, а `expression` не должен быть указан.  
  
 В `Function`, `Get`или `Operator` инструкция `Return` должна включать `expression`, а `expression` должен иметь тип данных, преобразуемый в возвращаемый тип процедуры. В `Function` или `Get` можно также назначить выражение для имени процедуры, которое будет использоваться в качестве возвращаемого значения, а затем выполнить инструкцию `Exit Function` или `Exit Property`. В `Operator` процедуре необходимо использовать `Return expression`.  
  
 В той же процедуре можно включить столько `Return` инструкций, сколько необходимо.  
  
> [!NOTE]
> Код в блоке `Finally` выполняется после того, как обнаруживается инструкция `Return` в блоке `Try` или `Catch`, но перед выполнением этой инструкции `Return`. Инструкция `Return` не может быть включена в блок `Finally`.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Return` используется несколько раз для возврата к вызывающему коду, если процедура не должна выполнять никаких других действий.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>См. также

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
