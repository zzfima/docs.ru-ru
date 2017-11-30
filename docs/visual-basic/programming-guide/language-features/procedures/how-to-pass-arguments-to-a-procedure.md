---
title: "Практическое руководство. Передача аргументов в процедуру (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3debb4fa6e7b15f9c321ef207d0cc04181a98da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Практическое руководство. Передача аргументов в процедуру (Visual Basic)
При вызове процедуры следовать имя процедуры со списком аргументов в скобки. Необходимо указать аргумент, соответствующий каждому обязательному параметру определяемого этой процедурой, и при необходимости можно указать дополнительные аргументы для `Optional` параметров. Если не указать `Optional` параметра в вызове, необходимо включить запятую, чтобы отметить его место в списке аргументов, если указываются все последующие аргументы.  
  
 Если требуется передать аргумент типа данных отличается от соответствующего параметра, такие как `Byte` для `String`, можно задать для ключа проверки типов ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) для `Off`. Если `Option Strict` — `On`, необходимо использовать либо расширяющих преобразований, либо ключевые слова явное преобразование. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Чтобы передать один или несколько аргументов в процедуру  
  
1.  В операторе вызова после имени процедуры со скобками.  
  
2.  Заключенный в круглые скобки, поместите список аргументов. Включить аргумент для каждого обязательного параметра, определяемого этой процедурой, а аргументы должны разделяться запятыми.  
  
3.  Убедитесь, что каждый аргумент имеет допустимое выражение, результатом вычисления которого преобразуется в тип процедуры определяет для соответствующего параметра.  
  
4.  Если параметр определен как [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md), можно включить его в списке аргументов или удалите его. Если он опущен, процедура будет использовать значение по умолчанию, определенное для этого параметра.  
  
5.  Если не указан аргумент для `Optional` параметр и в списке параметров после него имеется еще один параметр, можно отметить место пропущенный аргумент по Лишняя запятая в списке аргументов.  
  
     В следующем примере вызывается [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> функции.  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     В предыдущем примере передается обязательный первый аргумент, который является строкой сообщения для отображения. Он указывается аргумент для необязательный второй параметр, который определяет кнопки, отображаемые в окне сообщения. Так как вызов не предоставляет значение, `MsgBox` использует значение по умолчанию `MsgBoxStyle.OKOnly`, отображающий только **ОК** кнопки.  
  
     Вторая запятая в списке аргументов отмечает место пропущенного второго параметра, а последняя строка передается необязательный третий параметр `MsgBox`, содержит текст, отображаемый в заголовке окна.  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры функций](./function-procedures.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Процедуры операторов](./operator-procedures.md)  
 [Практическое руководство. Определение параметра для процедуры](./how-to-define-a-parameter-for-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Рекурсивные процедуры](./recursive-procedures.md)  
 [Перегрузка процедур](./procedure-overloading.md)  
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Объектно-ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
