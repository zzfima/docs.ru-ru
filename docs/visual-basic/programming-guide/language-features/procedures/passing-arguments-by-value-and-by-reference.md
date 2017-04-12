---
title: "Передача аргументов по значению и по ссылке (Visual Basic) | Документы Microsoft"
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 56d1ceba14020ca7f3dc750c2318efd3e9586af0
ms.lasthandoff: 03/13/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Передача аргументов по значению и по ссылке (Visual Basic)
В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], можно передать аргумент в процедуру *по значению* или *по ссылке*. Это называется *механизм передачи*, и определяет, является ли процедура может изменять программный элемент, лежащий в основе аргумента в вызывающем коде. Объявление процедуры определяет механизм передачи для каждого параметра, указав [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово.  
  
## <a name="distinctions"></a>Различия между устройствами  
 При передаче аргумента в процедуру, следует учитывать несколько отличительных особенностей, которые взаимодействуют друг с другом.  
  
-   Является ли базовый элемент программирования изменяемым или неизменяемым  
  
-   Является ли сам аргумент изменяемым или неизменяемым  
  
-   Является ли аргумент передается по значению или по ссылке  
  
-   Является ли тип данных аргумента типом значения или ссылочным типом  
  
 Дополнительные сведения см. в разделе [различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md) и [различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Выбор механизма передачи  
 Необходимо выбрать механизм передачи тщательно для каждого аргумента.  
  
-   **Защита**. При выборе между двумя механизмами передачи, наиболее важный критерий является раскрытие вызова переменных для изменения. Преимущество передачи аргумента `ByRef` является, что процедура может возвратить значение в вызывающий код через этот аргумент. Преимущество передачи аргумента `ByVal` является, что в этом случае переменная защищена от изменений, вносимых в процедуре.  
  
-   **Производительность**. Несмотря на то, что механизм передачи может повлиять на производительность кода, разница не заметна. Единственным исключением является передача типа значения `ByVal`. В этом случае [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] копирует все содержимое аргумента. Таким образом, для типа больших значений, например структуры, он может быть более эффективным для ее передачи `ByRef`.  
  
     Указатель на данные работает для ссылочных типов, скопированные (4 байта на 32-разрядных платформах, восемь байтов на 64-разрядных платформах). Таким образом, можно передавать аргументы типа `String` или `Object` по значению без потери производительности.  
  
## <a name="determination-of-the-passing-mechanism"></a>Определение алгоритма передачи  
 Объявление процедуры определяет механизм передачи для каждого параметра. Вызывающий код не может изменить `ByVal` механизм.  
  
 Если параметр объявлен с `ByRef`, вызывающий код может заставить механизм `ByVal` , заключив имя аргумента в скобки в вызове. Дополнительные сведения см. в разделе [как: Принудительная передача аргумента передается значение](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Когда передавать аргумент по значению  
  
-   Если элемент кода вызова, содержащийся в аргументе, является неизменяемым, объявите соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Код не может изменить значение неизменяемого элемента.  
  
-   Если элемент является изменяемым, но нежелательно процедуру, чтобы иметь возможность изменить его значение, объявите параметр `ByVal`. Только вызывающий код может изменить значение изменяемого элемента, передаются по значению.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Когда передавать аргумент по ссылке  
  
-   Если процедуре необходимо изменить базовый элемент в коде вызова, объявите соответствующий параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Если правильное выполнение кода зависит от изменения базового элемента в вызывающем коде процедуры, объявите параметр `ByRef`. Если при передаче по значению или код вызова переопределяет `ByRef` механизма передачи, заключив аргумент в круглые скобки, вызов процедуры может привести к непредсказуемым результатам.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показано, когда передача аргументов по значению, а когда передавать их по ссылке. Процедура `Calculate` имеет оба `ByVal` и `ByRef` параметр. Дана процентная ставка, `rate`и суммы денег, `debt`, задачей процедуры является вычисление нового значения для `debt` , являющееся результатом применения процентной ставки к исходному значению `debt`. Поскольку `debt` — `ByRef` параметр, новая сумма отражается в значении аргумента в вызывающем коде, который соответствует `debt`. Параметр `rate` — `ByVal` параметр поскольку `Calculate` не следует менять его значение.  
  
### <a name="code"></a>Код  
 [!code-vb[VbVbcnProcedures&#74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)   
 [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
