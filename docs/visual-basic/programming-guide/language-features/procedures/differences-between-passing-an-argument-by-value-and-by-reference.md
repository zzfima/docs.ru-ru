---
title: "Различия между передачей аргумента по значению и по ссылке (Visual Basic) | Документы Microsoft"
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
- procedures, passing arguments
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
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
ms.openlocfilehash: 93c515dd8524cde85555a27879baee00185f78e3
ms.lasthandoff: 03/13/2017

---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Различия между передачей аргумента по значению и по ссылке (Visual Basic)
При передаче одного или нескольких аргументов в процедуру, каждый аргумент соответствует базовому элементу программирования в вызывающем коде. Можно передать либо значение этого базового элемента, либо ссылку на него. Это называется *механизм передачи*.  
  
## <a name="passing-by-value"></a>передача по значению  
 При передаче аргумента *по значению* , указав [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ключевое слово для соответствующего параметра в определении процедуры. При использовании этого механизма передачи [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] копирует значение из базового элемента программирования в локальную переменную в процедуре. Код процедуры не имеет доступа к базовому элементу в вызывающем коде.  
  
## <a name="passing-by-reference"></a>Передача по ссылке  
 При передаче аргумента *по ссылке* , указав [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово для соответствующего параметра в определении процедуры. При использовании этого механизма передачи [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет процедуре прямую ссылку на основной элемент программирования в вызывающий код.  
  
## <a name="passing-mechanism-and-element-type"></a>Механизм передачи и тип элемента  
 Выбор механизма передачи отличается от классификации типа базового элемента. Передача по значению или по ссылке указывает на то, что [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет коду процедуры. Тип значения или ссылочный тип ссылается на способ хранения элемента программирования в памяти.  
  
 Однако механизм передачи и тип элемента являются взаимосвязанными. Значение ссылочного типа — указатель на данные в другом месте в памяти. Это означает, что при передаче ссылочного типа по значению код процедуры имеет указатель на базовые данные элемента, даже если нет доступа к самому базовому элементу. Например если элемент является переменной массива, код процедуры не имеет доступа к самой переменной, но он имеет доступ к членам массива.  
  
## <a name="ability-to-modify"></a>Возможность изменения  
 Когда неизменяемый элемент передается в качестве аргумента, процедура не может изменить его в вызывающем коде, был ли он передан `ByVal` или `ByRef`.  
  
 Для изменяемого элемента в следующей таблице перечислены взаимодействия тип элемента и механизм передачи.  
  
|Тип элемента|Передан`ByVal`|Передан`ByRef`|  
|------------------|--------------------|--------------------|  
|Тип значения (содержит только значение)|Процедура не может изменять переменную или любого из его элементов.|Процедура может изменять переменную и ее членов.|  
|Ссылочный тип (содержит указатель на экземпляр класса или структуры)|Процедура не может изменить переменную, но можно изменить члены экземпляра, на который он указывает.|Процедура может изменять переменную и члены экземпляра, на который он указывает.|  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)   
 [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
