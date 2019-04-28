---
title: Практическое руководство. Передача аргументов в процедуру (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 012ad8e6229958575030ee820a3b0b79cc50facc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863445"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Практическое руководство. Передача аргументов в процедуру (Visual Basic)
При вызове процедуры, необходимо выполнить имя процедуры со списком аргументов в скобках. Необходимо указать аргумент, соответствующий каждому обязательному параметру в процедуре можно определить, и при необходимости можно указать аргументы для `Optional` параметров. Если вы не предоставляете `Optional` параметра в вызове, необходимо включить запятую, чтобы отметить его место в списке аргументов, если указываются все последующие аргументы.  
  
 Если требуется передать аргумент типа данных отличается от соответствующего параметра, такие как `Byte` для `String`, можно задать для ключа проверки типов ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) для `Off`. Если `Option Strict` является `On`, необходимо использовать либо расширяющих преобразований, либо ключевые слова явное преобразование. Дополнительные сведения см. в разделе [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Чтобы передать один или несколько аргументов в процедуру  
  
1. В операторе вызова после имени процедуры со скобками.  
  
2. В скобках, поместите список аргументов. Включить аргумент для каждого обязательного параметра, определяемого этой процедурой, а аргументы необходимо разделять запятыми.  
  
3. Убедитесь, что каждый аргумент является допустимое выражение, результатом вычисления которого преобразуется в тип процедуры определяются для соответствующего параметра.  
  
4. Если параметр определен как [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md), можно включить его в списке аргументов или пропустите его. Если он пропущен, процедура будет использовать значение по умолчанию, определенное для этого параметра.  
  
5. Если опустить аргумент для `Optional` параметр и в списке параметров после него имеется еще один параметр, можно пометить вместо пропущенный аргумент с лишнюю запятую в списке аргументов.  
  
     В следующем примере вызывается Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> функции.  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     В предыдущем примере передается обязательный первый аргумент, являющийся строку сообщения для отображения. Он указывается аргумент для необязательный второй параметр, указывающий кнопки, отображаемые в окне сообщения. Поскольку вызов не передается значение, `MsgBox` используется значение по умолчанию, `MsgBoxStyle.OKOnly`, отображающий только **ОК** кнопку.  
  
     Вторая запятая в списке аргументов отмечает место пропущенного второго параметра, а последняя строка передается третий необязательный параметр `MsgBox`, который является текст, отображаемый в заголовке окна.  
  
## <a name="see-also"></a>См. также

- [Подпрограммы](./sub-procedures.md)
- [Процедуры функций](./function-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение параметра для процедуры](./how-to-define-a-parameter-for-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Рекурсивные процедуры](./recursive-procedures.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)
