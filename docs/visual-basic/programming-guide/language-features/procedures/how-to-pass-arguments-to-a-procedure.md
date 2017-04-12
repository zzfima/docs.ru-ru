---
title: "Практическое руководство: передача аргументов в процедуру (Visual Basic) | Документы Microsoft"
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
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: ddccd476b2347368d0435f637edf3882db306f45
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Практическое руководство. Передача аргументов в процедуру (Visual Basic)
При вызове процедуры, то после имени процедуры со списком аргументов в скобках. Указать аргумент, соответствующий каждому обязательному параметру процедура определяет, и можно также указать дополнительные аргументы для `Optional` параметров. Если не указать `Optional` параметр в вызове, необходимо включить запятую, чтобы отметить его место в списке аргументов, если указываются все последующие аргументы.  
  
 Если требуется передать аргумент типа данных отличается от соответствующего параметра, такие как `Byte` для `String`, можно задать для ключа проверки типов ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) для `Off`. Если `Option Strict` — `On`, необходимо использовать либо расширяющих преобразований, либо явное преобразование ключевых слов. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Для передачи одного или нескольких аргументов в процедуру  
  
1.  В операторе вызова после имени процедуры со скобками.  
  
2.  Внутри скобок поместите список аргументов. Включать аргумент для каждого обязательного параметра, определяемого процедурой и аргументов необходимо разделять запятыми.  
  
3.  Убедитесь, что каждый аргумент имеет допустимое выражение, результатом вычисления которого преобразуется в тип процедуры определяет для соответствующего параметра.  
  
4.  Если параметр определен как [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md), можно либо включить его в список аргументов или пропустить. Если он опущен, процедура использует значение по умолчанию, определенное для этого параметра.  
  
5.  Если не указан аргумент для `Optional` параметр и в списке параметров после него имеется еще один параметр, можно отметить место пропущенного аргумента по лишнюю запятую в списке аргументов.  
  
     В следующем примере вызывается [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>функция.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
     [!code-vb[VbVbcnProcedures&#34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     В предыдущем примере передается обязательный первый аргумент, который является строкой сообщения для отображения. Он пропускается необязательный второй параметр, который указывает кнопки, отображаемые в окне сообщения. Поскольку в вызове не передается значение, `MsgBox` использует значение по умолчанию `MsgBoxStyle.OKOnly`, которая отображает только **ОК** кнопки.  
  
     Вторая запятая в списке аргументов отмечает место пропущенного второго параметра, а последняя строка передается в третий необязательный параметр `MsgBox`, который является текст, отображаемый в строке заголовка.  
  
## <a name="see-also"></a>См. также  
 [Sub-процедуры](./sub-procedures.md)   
 [Процедуры функций](./function-procedures.md)   
 [Процедуры свойств](./property-procedures.md)   
 [Процедуры операторов](./operator-procedures.md)   
 [Практическое руководство: определение параметра для процедуры](./how-to-define-a-parameter-for-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)   
 [Рекурсивные процедуры](./recursive-procedures.md)   
 [Перегрузка процедур](./procedure-overloading.md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Объектно-ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
