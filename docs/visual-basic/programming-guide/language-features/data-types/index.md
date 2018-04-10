---
title: Типы данных в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20a24c8632e1f2193cfa86319a824dfcc038d9d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-in-visual-basic"></a>Типы данных в Visual Basic
*Тип данных* программного элемента определяет данные, которые он может содержать, а также способ их хранения. Типы данных применяются ко всем значениям, которые могут храниться в памяти компьютера или участвовать в вычислении выражения. Все переменные, литералы, константы, перечисления, свойства, параметры и аргументы процедуры, а также возвращаемые значения процедуры относятся к определенному типу данных.  
  
## <a name="declared-data-types"></a>Объявленные типы данных  
 Программный элемент определяется с помощью оператора объявления, а его тип данных указывается с помощью предложения `As`. В таблице ниже приведены инструкции, которые используются для объявления разных элементов.  
  
|Программный элемент|Объявление типа данных|  
|-------------------------|---------------------------|  
|Переменная|В [операторе Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Литерал|С помощью символа типа литерала; см. [символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Константа|В [операторе Const](../../../../visual-basic/language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Перечисление|В [операторе Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Свойство|В [операторе Property](../../../../visual-basic/language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Параметр процедуры|В [операторе Sub](../../../../visual-basic/language-reference/statements/sub-statement.md), [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md) или [инструкции Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Аргумент процедуры|В вызывающем коде; все аргументы являются уже объявленными элементами программирования или выражениями, содержащими объявленные элементы<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Возвращаемое значение процедуры|В [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md) или [инструкции Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 См. список [типов данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) Visual Basic  
  
## <a name="see-also"></a>См. также  
 [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Кортежи](tuples.md)     
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
