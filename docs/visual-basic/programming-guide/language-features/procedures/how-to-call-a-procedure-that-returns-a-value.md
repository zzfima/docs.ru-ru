---
title: "Практическое руководство: вызов процедуры, возвращающей значение (Visual Basic) | Документы Microsoft"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
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
ms.openlocfilehash: df6bb1ed8acf5f86a290d67fec9c053cfe5245d2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic)
A `Function` процедура возвращает значение в вызывающий код. Можно вызвать его, включая ее имя и аргументы справа от оператора присваивания или в составе выражения.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Чтобы вызвать процедуру Function в выражении  
  
1.  Использовать `Function` так же, как бы переменной имя процедуры. Можно использовать `Function` вызов процедуры везде, где можно использовать переменную или константу в выражении.  
  
2.  После имени процедуры с заключенным в списке аргументов скобки. Если не указано никаких аргументов, скобки можно опустить. Однако с помощью скобок делает код более удобными для чтения.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, `Function` процедуры определены соответствующие параметры.  
  
     Кроме того можно передать один или несколько аргументов по имени. Дополнительные сведения см. в разделе [передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md).  
  
4.  Значение, возвращаемое процедурой участвует в выражении, как и значение переменной или константа.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Чтобы вызвать процедуру Function в операторе присваивания  
  
1.  Используйте `Function` имя процедуры после равенства (`=`) входа в операторе присваивания.  
  
2.  После имени процедуры с заключенным в списке аргументов скобки. Если не указано никаких аргументов, скобки можно опустить. Однако с помощью скобок делает код более удобными для чтения.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, `Function` процедура определяет соответствующие им параметры, если только не используется их передача по имени.  
  
4.  Значение, возвращаемое процедурой, хранится в переменной или свойстве в левой части оператора присваивания.  
  
## <a name="example"></a>Пример  
 В следующем примере вызывается [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>для получения значения переменной среды операционной системы.</xref:Microsoft.VisualBasic.Interaction.Environ%2A> Первая строка вызывает `Environ` в выражении, а вторая строка вызывает его в операторе присваивания. `Environ`принимает имя переменной в качестве единственного аргумента. Значение переменной возвращается в вызывающий код.  
  
 [!code-vb[VbVbcnProcedures&#7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры функций](./function-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Практическое руководство: создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Практическое руководство: возвращаемое значение из процедуры](./how-to-return-a-value-from-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)
