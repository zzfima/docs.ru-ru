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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956935"
---
# <a name="exit-statement-visual-basic"></a>Оператор Exit (Visual Basic)

Выходит из процедуры или блока и немедленно передает управление оператору после вызова процедуры или определения блока.

## <a name="syntax"></a>Синтаксис

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>Операторы

 `Exit Do`  
 Немедленно завершает работу цикла `Do`, в котором он отображается. Выполнение продолжится с оператора, следующего за оператором `Loop`. `Exit Do` можно использовать только в цикле `Do`. При использовании внутри вложенных циклов `Do` `Exit Do` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.

 `Exit For`  
 Немедленно завершает работу цикла `For`, в котором он отображается. Выполнение продолжится с оператора, следующего за оператором `Next`. `Exit For` может использоваться только в цикле `For`... `Next` или `For Each`... `Next`. При использовании внутри вложенных циклов `For` `Exit For` выходит из внутреннего цикла и передает управление следующему более высокому уровню вложенности.

 `Exit Function`  
 Немедленно завершает работу процедуры `Function`, в которой она отображается. Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей процедуру `Function`. `Exit Function` может использоваться только внутри процедуры `Function`.

 Чтобы указать возвращаемое значение, можно присвоить значение имени функции в строке перед оператором `Exit Function`. Чтобы присвоить возвращаемое значение и выйти из функции в одной инструкции, можно использовать [оператор return](return-statement.md).

 `Exit Property`  
 Немедленно завершает работу процедуры `Property`, в которой она отображается. Выполнение продолжится с оператора, вызвавшего процедуру `Property`, то есть с инструкцией, запрашивающей или задавая значение свойства. `Exit Property` может использоваться только внутри процедуры свойства `Get` или `Set`.

 Чтобы указать возвращаемое значение в процедуре `Get`, можно присвоить значение имени функции в строке перед оператором `Exit Property`. Чтобы присвоить возвращаемое значение и выйти из процедуры `Get` в одном операторе, можно использовать инструкцию `Return`.

 В процедуре `Set` Инструкция `Exit Property` эквивалентна инструкции `Return`.

 `Exit Select`  
 Немедленно завершает работу блока `Select Case`, в котором он отображается. Выполнение продолжится с оператора, следующего за оператором `End Select`. `Exit Select` может использоваться только внутри оператора `Select Case`.

 `Exit Sub`  
 Немедленно завершает работу процедуры `Sub`, в которой она отображается. Выполнение продолжится с оператора, следующего за инструкцией, вызвавшей процедуру `Sub`. `Exit Sub` может использоваться только внутри процедуры `Sub`.

 В процедуре `Sub` Инструкция `Exit Sub` эквивалентна инструкции `Return`.

 `Exit Try`  
 Немедленно завершает работу блока `Try` или `Catch`, в котором он отображается. Выполнение продолжится с блока `Finally`, если таковой имеется, или с оператором, следующим за оператором `End Try` в противном случае. `Exit Try` можно использовать только в блоке `Try` или `Catch`, а не в блоке `Finally`.

 `Exit While`  
 Немедленно завершает работу цикла `While`, в котором он отображается. Выполнение продолжится с оператора, следующего за оператором `End While`. `Exit While` можно использовать только в цикле `While`. При использовании внутри вложенных циклов `While` `Exit While` передает управление циклу, который является одним вложенным уровнем над циклом, где происходит `Exit While`.

## <a name="remarks"></a>Примечания

Не путайте операторы `Exit` с операторами `End`. `Exit` не определяет конец инструкции.

## <a name="example"></a>Пример

В следующем примере условие цикла останавливает цикл, если переменная `index` больше 100. Однако оператор `If` в цикле приводит к тому, что оператор `Exit Do` останавливает цикл, если переменная индекса больше 10.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>Пример

В следующем примере возвращаемое значение присваивается имени функции `myFunction`, а затем для возврата из функции используется `Exit Function`.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>Пример

В следующем примере [оператор return](return-statement.md) используется для назначения возвращаемого значения и выхода из функции:

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>См. также

- [Оператор Continue](continue-statement.md)
- [Оператор Do...Loop](do-loop-statement.md)
- [Оператор End](end-statement.md)
- [Оператор For Each...Next](for-each-next-statement.md)
- [Оператор For...Next](for-next-statement.md)
- [Оператор Function](function-statement.md)
- [Оператор Return](return-statement.md)
- [Оператор Stop](stop-statement.md)
- [Оператор Sub](sub-statement.md)
- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
