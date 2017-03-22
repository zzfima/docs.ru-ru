---
title: "Практическое руководство: определение параметра для процедуры (Visual Basic) | Документы Microsoft"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
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
ms.openlocfilehash: 9fb9ad244499039c1768ff97f071168e0a0842e4
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Практическое руководство. Объявление параметра для процедуры (Visual Basic)
Объект *параметр* позволяет вызывающему коду передать значение в вызываемую процедуру при ее вызове. Каждый параметр процедуры объявляется так же, как объявить переменную, указав его имя и тип данных. Можно также указать механизм передачи, и параметр является необязательным.  
  
 Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Определение параметра процедуры  
  
1.  В объявлении процедуры добавьте имя параметра в список параметров процедуры, отделив его от других параметров запятыми.  
  
2.  Выберите тип данных параметра.  
  
3.  После имени параметра `As` предложение, чтобы указать тип данных.  
  
4.  Определите механизм передачи для параметра. Обычно необходимо передавать параметр по значению, если не требуется, чтобы иметь возможность изменить его значение в вызывающем коде процедуры.  
  
5.  Перед именем параметра с [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для указания механизм передачи. Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Если аргумент является необязательным, укажите перед механизмом передачи [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md) и соответствовать типу данных параметра со знака равенства (`=`) и значение по умолчанию.  
  
     В следующем примере определяется структура `Sub` процедуры с тремя параметрами. Первые два являются обязательными, а третий — необязательным. Объявления параметров в списке параметров разделяются запятыми.  
  
     [!code-vb[VbVbcnProcedures&#33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     Первый параметр принимает `customer` объекта, и `updateCustomer` может непосредственно обновлять переменную, передаваемую в `c` , так как аргумент передается [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Процедура не может изменить значения последних двух аргументов, поскольку они передаются [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Если вызывающий код не предоставляет значение для `level` параметр [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] устанавливает его значение по умолчанию 0.  
  
     Если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `Off`, `As` предложение необязательно при определении параметров. Однако если любой из параметров использует `As` предложение, их необходимо его использование. Если переключатель проверки типов имеет `On`, `As` предложение является обязательным для каждого определения параметра.  
  
     Задание типов данных для всех элементов программирования называется *строгой типизации*. При задании `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] обеспечивает строгую типизацию. Это настоятельно рекомендуется, по следующим причинам:  
  
    -   Он обеспечивает поддержку IntelliSense для переменных и параметров. Это позволяет видеть их свойства и другие члены, при вводе в коде.  
  
    -   Это позволяет компилятору выполнять проверку типов. Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения из-за ошибок, таких как переполнение. Обнаруживаются также вызовы методов для объектов, которые не поддерживают их.  
  
    -   Обеспечивается более быстрое выполнение кода. Одна из причин для этого является, если не указать тип данных для элемента программирования [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор присваивает его `Object` типа. Скомпилированному коду может потребоваться преобразовать вперед и назад между `Object` и других типов данных, что снижает производительность.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Sub-процедуры](./sub-procedures.md)   
 [Процедуры функций](./function-procedures.md)   
 [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)   
 [Рекурсивные процедуры](./recursive-procedures.md)   
 [Перегрузка процедур](./procedure-overloading.md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Объектно-ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
