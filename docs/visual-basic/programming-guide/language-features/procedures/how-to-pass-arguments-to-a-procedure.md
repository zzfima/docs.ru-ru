---
title: "Практическое руководство. Передача аргументов в процедуру (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "передача аргументов, процедуры"
  - "аргументы [Visual Basic], передача процедурам"
  - "аргументы процедур"
  - "параметры процедуры"
  - "процедуры, аргументы"
  - "процедуры, вызов"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Практическое руководство. Передача аргументов в процедуру (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

При вызове процедуры вы указываете имя процедуры со списком аргументов в круглых скобках.  Необходимо указать аргумент, соответствующий каждому обязательному параметру, определяемому процедурой, и можно также указать дополнительные аргументы для параметров `Optional`.  Если в вызове не указывается параметр `Optional`, необходимо включить запятую, чтобы отметить его место в списке аргументов, если указываются какие\-либо последующие аргументы.  
  
 Если планируется передача аргумента типа данных, отличающегося от соответствующего параметра, например `Byte` в `String`, можно задать для ключа проверки типов \([Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) значение `Off`.  Если `Option Strict` имеет значение `On`, необходимо использовать ключевые слова либо расширяющих преобразований, либо явных преобразований.  Дополнительные сведения см. в разделах [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Дополнительные сведения см. в разделе [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md).  
  
### Передача одного или нескольких аргументов в процедуру  
  
1.  В операторе вызова укажите скобки после имени процедуры.  
  
2.  Внутрь скобок поместите список аргументов.  Укажите через запятую аргументы для каждого обязательного параметра, определяемого процедурой.  
  
3.  Убедитесь, что каждый аргумент имеет допустимое выражение, результат которого преобразуется в тип, определяемый процедурой для соответствующего параметра.  
  
4.  Если параметр определен как [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), можно включить его в список аргументов или пропустить.  Если параметр пропускается, в процедуре используется значение по умолчанию, определенное для этого параметра.  
  
5.  Если пропускается аргумент для параметра `Optional`, и в списке параметров после него имеется еще один параметр, то можно отметить место пропущенного аргумента, поставив вместо него запятую в списке аргументов.  
  
     Следующий пример вызывает функцию <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     В предыдущем примере передается обязательный первый аргумент, который является строкой сообщения для отображения.  Затем пропускается необязательный второй параметр, который указывает кнопки, отображаемые в окне сообщения.  Поскольку в вызове не передается значение, `MsgBox` использует значение по умолчанию `MsgBoxStyle.OKOnly`, в котором отображается только кнопка **ОК**.  
  
     Вторая запятая в списке аргументов отмечает место пропущенного второго параметра, а последняя строка передается в третий необязательный параметр `MsgBox` и содержит текст, отображаемый в заголовке сообщения.  
  
## См. также  
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение параметра для процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Рекурсивные процедуры](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Объектно\-ориентированное программирование](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)