---
title: Оператор Exit (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638120"
---
# <a name="exit-statement-visual-basic"></a>Оператор Exit (Visual Basic)
Выходит из процедуры или блока и немедленно передает управление оператору после вызова процедуры или определения блока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>Операторы  
 `Exit Do`  
 Немедленно завершает работу `Do` цикл, в котором он содержится. Выполнение продолжается с оператор, следующий `Loop` инструкции. `Exit Do` можно использовать только внутри `Do` цикла. При использовании внутри вложенной `Do` циклы, `Exit Do` выходит из самого внутреннего цикла и передает управление повысить уровень вложенности.  
  
 `Exit For`  
 Немедленно завершает работу `For` цикл, в котором он содержится. Выполнение продолжается с оператор, следующий `Next` инструкции. `Exit For` можно использовать только внутри `For`... `Next` или `For Each`... `Next` цикла. При использовании внутри вложенной `For` циклы, `Exit For` выходит из самого внутреннего цикла и передает управление повысить уровень вложенности.  
  
 `Exit Function`  
 Немедленно завершает работу `Function` процедуры, в котором он находится. Выполнение продолжается с оператора, следующего за оператором, вызвавшим `Function` процедуры. `Exit Function` можно использовать только внутри `Function` процедуры.  
  
 Чтобы задать возвращаемое значение, можно присвоить значение имени функции в строке перед `Exit Function` инструкции. Чтобы назначить возвращаемое значение и выхода из функции в одной инструкции, можно использовать [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Немедленно завершает работу `Property` процедуры, в котором он находится. Выполнение продолжается с оператора, который вызывается `Property` процедуры, то есть с помощью инструкции запроса и установки значения свойства. `Exit Property` можно использовать только внутри свойства `Get` или `Set` процедуры.  
  
 Чтобы указать возвращаемое значение в `Get` процедуры, можно присвоить значение имени функции в строке перед `Exit Property` инструкции. Чтобы назначить возвращаемое значение и выхода `Get` процедуры в одной инструкции, можно вместо этого использовать `Return` инструкции.  
  
 В `Set` процедуре `Exit Property` оператор эквивалентен `Return` инструкции.  
  
 `Exit Select`  
 Немедленно завершает работу `Select Case` блока, в котором находится этот элемент. Выполнение продолжается с оператор, следующий `End Select` инструкции. `Exit Select` можно использовать только внутри `Select Case` инструкции.  
  
 `Exit Sub`  
 Немедленно завершает работу `Sub` процедуры, в котором он находится. Выполнение продолжается с оператора, следующего за оператором, вызвавшим `Sub` процедуры. `Exit Sub` можно использовать только внутри `Sub` процедуры.  
  
 В `Sub` процедуре `Exit Sub` оператор эквивалентен `Return` инструкции.  
  
 `Exit Try`  
 Немедленно завершает работу `Try` или `Catch` блока, в котором находится этот элемент. Выполнение продолжается с `Finally` блокировать, если таковой имеется, или оператор, следующий `End Try` инструкции, которые в противном случае. `Exit Try` можно использовать только внутри `Try` или `Catch` блока, а не внутри `Finally` блока.  
  
 `Exit While`  
 Немедленно завершает работу `While` цикл, в котором он содержится. Выполнение продолжается с оператор, следующий `End While` инструкции. `Exit While` можно использовать только внутри `While` цикла. При использовании внутри вложенной `While` циклы, `Exit While` передает управление в цикл, находящийся на один уровень выше цикла где `Exit While` происходит.  
  
## <a name="remarks"></a>Примечания  
 Не следует путать `Exit` инструкции с `End` инструкций. `Exit` не определяет конец оператора.  
  
## <a name="example"></a>Пример  
 В следующем примере, останавливающее цикл в условие цикла при `index` переменной превышает 100. `If` Оператора цикла, однако вызывает `Exit Do` инструкции для остановки цикла, когда переменная индекса превышает 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Пример  
 В следующем примере присваивается значение имени функции `myFunction`, а затем использует `Exit Function` для возврата из функции.  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) присвойте возвращаемое значение и выхода из функции.  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>См. также

- [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md)
- [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
