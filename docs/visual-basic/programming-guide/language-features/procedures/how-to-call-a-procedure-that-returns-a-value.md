---
title: Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbaaa5ed17845a7ac8847786fb10111c724015ba
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic)
Объект `Function` процедура возвращает значение вызывающему коду. Можно вызвать, включая ее имя и аргументы либо справа от оператора присваивания или в составе выражения.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Вызов процедуры, функции в выражении  
  
1.  Использовать `Function` так же, как переменную, имя процедуры. Можно использовать `Function` вызов процедуры в любом месте, переменной или константы можно использовать в выражении.  
  
2.  После имени процедуры с помощью скобок, заключите список аргументов. Если не указано никаких аргументов, скобки можно опустить. Однако с помощью скобок делает код более удобным для чтения.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, `Function` процедуры определены соответствующие параметры.  
  
     Кроме того можно передать один или несколько аргументов по имени. Дополнительные сведения см. в разделе [передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md).  
  
4.  Значение, возвращаемое процедурой участвует в выражении, как и значение переменной или константа.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Чтобы вызвать процедуру Function в операторе присваивания  
  
1.  Используйте `Function` имя процедуры после равенства (`=`) войти в операторе присваивания.  
  
2.  После имени процедуры с помощью скобок, заключите список аргументов. Если не указано никаких аргументов, скобки можно опустить. Однако с помощью скобок делает код более удобным для чтения.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, `Function` процедура определяет соответствующие им параметры, если вы передаете их по имени.  
  
4.  Значение, возвращаемое процедурой хранится в переменной или свойстве в левой части оператора присваивания.  
  
## <a name="example"></a>Пример  
 В следующем примере вызывается метод Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> для получения значения переменной среды операционной системы. Первая строка вызывает `Environ` внутри выражения, а вторая строка вызывает его в операторе присваивания. `Environ` принимает имя переменной в качестве единственного аргумента. Значение переменной возвращается в вызывающий код.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры функций](./function-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Практическое руководство. Возврат значения из процедуры](./how-to-return-a-value-from-a-procedure.md)  
 [Практическое руководство. Вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)
