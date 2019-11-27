---
title: Практическое руководство. Передача аргументов в процедуру
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
ms.openlocfilehash: 0267eed7c145988d61de715fd661bd4906d8d57d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344846"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Практическое руководство. Передача аргументов в процедуру (Visual Basic)
При вызове процедуры необходимо следовать имени процедуры со списком аргументов в круглых скобках. Укажите аргумент, соответствующий каждому обязательному параметру, определяемому процедурой, и при необходимости можно указать аргументы для параметров `Optional`. Если в вызове не указан параметр `Optional`, необходимо включить запятую, чтобы пометить ее место в списке аргументов, если вы предоставляете последующие аргументы.  
  
 Если предполагается передать аргумент типа данных, отличный от того, который соответствует его параметру, например `Byte` для `String`, можно установить для параметра проверки типов ([оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) значение `Off`. Если `Option Strict` `On`, необходимо использовать либо расширяющие преобразования, либо ключевые слова явного преобразования. Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Дополнительные сведения см. в разделе [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Передача одного или нескольких аргументов в процедуру  
  
1. В операторе вызова используйте имя процедуры с круглыми скобками.  
  
2. Внутри круглых скобок вставьте список аргументов. Включите аргумент для каждого обязательного параметра, определяемого процедурой, и разделите аргументы запятыми.  
  
3. Убедитесь, что каждый аргумент является допустимым выражением, результатом которого является тип данных, преобразуемый в тип, определяемый процедурой для соответствующего параметра.  
  
4. Если параметр определен как [необязательный](../../../../visual-basic/language-reference/modifiers/optional.md), его можно включить в список аргументов или опустить. Если опустить его, процедура использует значение по умолчанию, определенное для этого параметра.  
  
5. Если опустить аргумент для параметра `Optional` и после него в списке параметров есть другой параметр, можно пометить место пропущенного аргумента на дополнительную запятую в списке аргументов.  
  
     В следующем примере вызывается функция Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     В предыдущем примере предоставляется обязательный первый аргумент, который представляет собой отображаемую строку сообщения. Он опускает аргумент для необязательного второго параметра, который указывает кнопки, отображаемые в окне сообщения. Поскольку вызов не предоставляет значение, `MsgBox` использует значение по умолчанию `MsgBoxStyle.OKOnly`, которое отображает только кнопку **ОК** .  
  
     Вторая запятая в списке аргументов отмечает место пропущенного второго аргумента, а последняя строка передается необязательному третьему параметру `MsgBox`, который является текстом, отображаемым в заголовке окна.  
  
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
