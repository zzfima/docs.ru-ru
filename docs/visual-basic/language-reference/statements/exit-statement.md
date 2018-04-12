---
title: Оператор Exit (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2df63ecbf0605d07296e1692f18b1b015e27cd03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="exit-statement-visual-basic"></a>Оператор Exit (Visual Basic)
Выходит из процедуры или блока и немедленно передает управление оператору после вызова процедуры или определения блока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>Операторы  
 `Exit Do`  
 Немедленно завершает работу `Do` цикл, в котором он содержится. Выполнение продолжается с оператору, следующему `Loop` инструкции. `Exit Do`можно использовать только внутри `Do` цикла. При использовании внутри вложенной `Do` циклы, `Exit Do` выходит из самого внутреннего цикла и передает управление верхнего уровня вложенности.  
  
 `Exit For`  
 Немедленно завершает работу `For` цикл, в котором он содержится. Выполнение продолжается с оператору, следующему `Next` инструкции. `Exit For`можно использовать только внутри `For`... `Next` или `For Each`... `Next` цикла. При использовании внутри вложенной `For` циклы, `Exit For` выходит из самого внутреннего цикла и передает управление верхнего уровня вложенности.  
  
 `Exit Function`  
 Немедленно завершает работу `Function` процедуры, в котором он отображается. Выполнение продолжается с оператора, следующего за оператором, вызвавшим `Function` процедуры. `Exit Function`можно использовать только внутри `Function` процедуры.  
  
 Чтобы задать возвращаемое значение, можно назначить значение имени функции в строке перед `Exit Function` инструкции. Чтобы назначить возвращаемое значение и выхода из функции в одной инструкции, вместо этого можно использовать [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Немедленно завершает работу `Property` процедуры, в котором он отображается. Выполнение продолжается с оператора, который называется `Property` процедуры, то есть с помощью инструкции запроса и установки значения свойства. `Exit Property`может использоваться только внутри свойства `Get` или `Set` процедуры.  
  
 Чтобы указать значение, возвращаемое в `Get` процедуры, можно присвоить значение имени функции в строке перед `Exit Property` инструкции. Чтобы назначить возвращаемое значение и выйти `Get` процедура в одной инструкции можно использовать `Return` инструкции.  
  
 В `Set` процедуре `Exit Property` оператор эквивалентен `Return` инструкции.  
  
 `Exit Select`  
 Немедленно завершает работу `Select Case` блока, в котором находится этот элемент. Выполнение продолжается с оператору, следующему `End Select` инструкции. `Exit Select`можно использовать только внутри `Select Case` инструкции.  
  
 `Exit Sub`  
 Немедленно завершает работу `Sub` процедуры, в котором он отображается. Выполнение продолжается с оператора, следующего за оператором, вызвавшим `Sub` процедуры. `Exit Sub`можно использовать только внутри `Sub` процедуры.  
  
 В `Sub` процедуре `Exit Sub` оператор эквивалентен `Return` инструкции.  
  
 `Exit Try`  
 Немедленно завершает работу `Try` или `Catch` блока, в котором находится этот элемент. Выполнение продолжается с `Finally` блокировать при наличии такового или с оператору, следующему `End Try` инструкции, которые в противном случае. `Exit Try`можно использовать только внутри `Try` или `Catch` блока, а не внутри `Finally` блока.  
  
 `Exit While`  
 Немедленно завершает работу `While` цикл, в котором он содержится. Выполнение продолжается с оператору, следующему `End While` инструкции. `Exit While`можно использовать только внутри `While` цикла. При использовании внутри вложенной `While` циклы, `Exit While` передает управление в цикл, находящийся на один уровень выше цикла где `Exit While` происходит.  
  
## <a name="remarks"></a>Примечания  
 Не следует путать `Exit` инструкции с `End` инструкции. `Exit`не определяет конец оператора.  
  
## <a name="example"></a>Пример  
 В следующем примере условия цикла останавливающее цикл при `index` переменной больше 100. `If` Инструкции в цикле, однако вызывает `Exit Do` инструкции для остановки цикла, когда переменная индекса превышает 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере возвращаемое значение присваивается имени функции `myFunction`, а затем использует `Exit Function` для возврата из функции.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) назначить возвращаемое значение и выхода из функции.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)  
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md)  
 [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
