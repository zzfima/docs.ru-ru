---
title: "Практическое руководство. Объявление параметра для процедуры (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c909cfe1b45a42aae91948917f310474575f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Практическое руководство. Объявление параметра для процедуры (Visual Basic)
Объект *параметр* позволяет вызывающему коду значение передается в процедуру при ее вызове. Каждый параметр процедуры объявляется так же, как объявить переменную, указав его имя и тип данных. Можно также задать способ передачи, и параметр является необязательным.  
  
 Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Определение параметра процедуры  
  
1.  В объявлении процедуры добавьте имя параметра в список параметров процедуры, отделив его от других параметров запятыми.  
  
2.  Выберите тип данных параметра.  
  
3.  После имени параметра `As` предложений, чтобы указать тип данных.  
  
4.  Определите механизм передачи для параметра. Обычно необходимо передавать параметр по значению, если не требуется, чтобы иметь возможность изменить его значение в вызывающем коде процедуры.  
  
5.  Перед именем параметра [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для указания механизм передачи. Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Если аргумент является необязательным, укажите перед механизмом передачи [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) и следуйте тип данных параметра со знака равенства (`=`) и значение по умолчанию.  
  
     В следующем примере определяется по контуру `Sub` процедуры с тремя параметрами. Первые два являются обязательными, а третий — необязательным. Объявления параметра в списке параметров разделяются запятыми.  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     Первый параметр принимает `customer` объекта, и `updateCustomer` может непосредственно обновлять переменную, передаваемую в `c` потому, что аргумент передается [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Процедура не может изменить значения последних двух аргументов, поскольку они передаются [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Если вызывающий код не предоставляет значение для `level` параметр [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] устанавливает его значение по умолчанию 0.  
  
     Если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `Off`, `As` предложение необязательно при определении параметров. Тем не менее если любой из параметров использует `As` предложения, все из них необходимо использовать его. Если ключ проверки типа `On`, `As` предложение является обязательным для каждого определения параметра.  
  
     Задание типов данных для всех элементов программирования называется *строгую типизацию*. При задании `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] обеспечивает строгую типизацию. Это настоятельно рекомендуется, по следующим причинам:  
  
    -   Она включает поддержку IntelliSense для переменных и параметров. Это позволяет видеть свойства и другие члены, вводимые в коде.  
  
    -   Это позволяет компилятору выполнять проверку типов. Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение. Он также обнаруживаются вызовы методов для объектов, которые не поддерживают.  
  
    -   Это приводит к более быстрое выполнение кода. Одна из причин для этого: Если не указать тип данных для элемента программирования [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятор назначает его `Object` типа. Скомпилированному коду может потребоваться преобразовать и переключений между `Object` и других типов данных, что снижает производительность.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры функций](./function-procedures.md)  
 [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Рекурсивные процедуры](./recursive-procedures.md)  
 [Перегрузка процедур](./procedure-overloading.md)  
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Объектно-ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
