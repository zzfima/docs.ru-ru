---
title: "Вызов свойства или метода с помощью строкового имени (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87af2816ba42e2901c53bec5e9c19f34c676ed5c
ms.lasthandoff: 03/13/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Вызов свойства или метода с помощью строкового имени (Visual Basic)
В большинстве случаев доступ к свойствам и методам объекта во время разработки и писать код для их обработки. Однако в некоторых случаях может не известно, какие свойства и методы объекта заранее или необходима гибкость конечному пользователю для указания свойств или выполнения методов во время выполнения.  
  
## <a name="callbyname-function"></a>CallByName-функция  
 Рассмотрим, например, клиентское приложение, которое вычисляет выражения, введенные пользователем с помощью передачи оператора COM-компонент. Предположим, что постоянно добавляются новые функции для компонентов, которым необходимы новые операторы. При использовании методов доступа к объекту standard, необходимо перекомпилировать и переустановке клиентского приложения, прежде чем его можно будет использовать. Чтобы избежать этого, можно использовать `CallByName` функции для передачи новых операторов в виде строк без изменения приложения.  
  
 `CallByName` Функция позволяет использовать строку для указания свойства или метода во время выполнения. Сигнатура для `CallByName` выглядит следующим образом:  
  
 *Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())  
  
 Первый аргумент, *объекта*, принимает имя объекта, нужно действовать. *ProcedureName* аргумент принимает строку, содержащую имя метода или свойства вызываемой процедуры. *CallType* аргумент принимает константу, представляющую тип процедуры для вызова: метод (`Microsoft.VisualBasic.CallType.Method`), чтение свойства (`Microsoft.VisualBasic.CallType.Get`), или свойства (`Microsoft.VisualBasic.CallType.Set`). *Аргументы* аргумент, который является необязательным, принимает массив объектов типа `Object` , содержащий любые аргументы для процедуры.  
  
 Можно использовать `CallByName` с классами в текущем решении, но чаще всего используется для доступа к объектам COM или объектам из [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки.  
  
 Предположим, добавьте ссылку на сборку, содержащую класс с именем `MathClass`, который имеет новую функцию с именем `SquareRoot`, как показано в следующем коде:  
  
 [!code-vb[VbVbalrOOP&#53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 Приложение может использовать текстовые поля для элемента управления, какой метод будет вызван и ее аргументов. Например если `TextBox1` содержит выражение для вычисления, и `TextBox2` — используется для ввода имени функции, можно использовать следующий код для вызова `SquareRoot` выражения в `TextBox1`:  
  
 [!code-vb[VbVbalrOOP&#54;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Если ввести «64» в `TextBox1`, «SquareRoot» в `TextBox2`и затем вызвать `CallMath` процедура, квадратный корень числа в `TextBox1` вычисляется. Код в примере вызывает `SquareRoot` функции (которая принимает строку, содержащую выражение, проверяемое как обязательный аргумент) и возвращает «8» в `TextBox1` (квадратный корень из 64). Конечно, если пользователь введет недопустимую строку в `TextBox2`, если строка содержит имя свойства вместо метода или если метод имеет дополнительный аргумент, то во время выполнения возникает ошибка. Необходимо добавить надлежащий код обработки ошибок при использовании `CallByName` чтобы реагировать на эти или другие ошибки.  
  
> [!NOTE]
>  Хотя `CallByName` функция может быть полезной в некоторых случаях, необходимо учитывать ее влияние на производительность — использование `CallByName` для вызова процедуры немного медленнее, чем вызов с поздним связыванием. Если вы вызываете функцию, которая вызывается несколько раз, например в цикле, `CallByName` может иметь существенно повлиять на производительность.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A>   
 [Определение типа объекта](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
