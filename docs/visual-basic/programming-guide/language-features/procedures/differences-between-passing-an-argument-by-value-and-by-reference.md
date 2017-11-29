---
title: "Различия между передачей аргумента по значению и по ссылке (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3efd4f41184287cdcd3d499712a857bee997c1a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Различия между передачей аргумента по значению и по ссылке (Visual Basic)
Если передать один или несколько аргументов в процедуру, каждый аргумент соответствует базовому элементу программирования в вызывающем коде. Можно передать значение этого базового элемента или ссылку на него. Это называется *механизм передачи*.  
  
## <a name="passing-by-value"></a>передача по значению  
 При передаче аргумента *по значению* , указав [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ключевое слово для соответствующего параметра в определении процедуры. При использовании этого механизма передачи [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] копирует значение из базового элемента программирования в локальную переменную в процедуре. Код процедуры не имеет доступа к базовому элементу в вызывающем коде.  
  
## <a name="passing-by-reference"></a>Передача по ссылке  
 При передаче аргумента *по ссылке* , указав [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово для соответствующего параметра в определении процедуры. При использовании этого механизма передачи [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] предоставляет процедуре прямую ссылку на основной элемент программирования в вызывающем коде.  
  
## <a name="passing-mechanism-and-element-type"></a>Механизм передачи и тип элемента  
 Выбор механизма передачи отличается от классификации базовый тип элемента. Передача по значению или по ссылке ссылается на то, что [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] предоставляет коду процедуры. Тип значения или ссылочный тип ссылается на способ хранения элемента программирования в памяти.  
  
 Однако механизм передачи и тип элемента взаимосвязаны. Значение ссылочного типа — указатель на данные в другом месте в памяти. Это означает, что при передаче ссылочного типа по значению, код процедуры имеет указатель на базовый элемент данных, несмотря на то, что он не может получить доступ к самому базовому элементу. Например если элемент является переменной массива, код процедуры не имеет доступа на саму переменную, но он имеет доступ к членам массива.  
  
## <a name="ability-to-modify"></a>Возможность изменения  
 Когда неизменяемый элемент передается в качестве аргумента, процедура не может изменить его в вызывающем коде ли оно передается `ByVal` или `ByRef`.  
  
 Для изменяемого элемента в следующей таблице перечислены взаимодействия тип элемента и механизм передачи.  
  
|Тип элемента|Переданный`ByVal`|Переданный`ByRef`|  
|------------------|--------------------|--------------------|  
|Тип значения (содержит только значение)|Процедура не может изменять переменной или любого из его элементов.|Процедура может изменять переменную и ее члены.|  
|Ссылочный тип (содержит указатель на экземпляр класса или структуры)|Процедура не может изменить переменную, но можно изменить члены экземпляра, на который он указывает.|Процедура может изменять переменную и члены экземпляра, на который он указывает.|  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Практическое руководство. Защита аргумента процедуры от изменений значения](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Практическое руководство. Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
