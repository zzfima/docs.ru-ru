---
title: "Различия между передачей аргумента по значению и по ссылке (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "аргументы [Visual Basic], передача по значению или по ссылке"
  - "ByRef - ключевое слово, передача аргументов по ссылке"
  - "ByVal - ключевое слово, передача аргументов по значению"
  - "процедуры, передача аргументов"
  - "код Visual Basic, процедуры"
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Различия между передачей аргумента по значению и по ссылке (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

При передаче одного или нескольких аргументов в процедуру каждый аргумент соответствует основному элементу программирования в коде вызова.  Можно передать либо значение этого базового элемента, либо ссылку на него.  Это называется *механизмом передачи*.  
  
## Передача по значению  
 При передаче аргумента *по значению* нужно указать ключевое слово [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для соответствующего параметра в определении процедуры.  При использовании этого механизма передачи [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] копирует значение из базового элемента программирования в локальную переменную процедуры.  Код процедуры не имеет доступа к основному элементу в коде вызова.  
  
## Передача по ссылке  
 При передаче аргумента *по ссылке* нужно указать ключевое слово [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для соответствующего параметра в определении процедуры.  При использовании этого механизма передачи [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет процедуре прямую ссылку на основной элемент программирования в коде вызова.  
  
## Механизм передачи и тип элемента  
 Выбор механизма передачи отличается от классификации типа базового элемента.  Передача по значению или по ссылке зависит от того, что [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] передает коду процедуры.  Тип значения и ссылочный тип указывают на способ хранения элемента программирования в памяти.  
  
 Однако механизм передачи и тип элемента являются взаимосвязанными.  Значение ссылочного типа — это указатель на данные, находящиеся в другом месте в памяти.  Это означает, что при передаче ссылочного типа по значению код процедуры имеет указатель на базовые данные элемента, даже если он не имеет доступа к самому базовому элементу.  Например, если элемент является переменной массива, код процедуры не имеет непосредственного доступа к переменной, но он получает доступ к членам массива.  
  
## Возможность изменения  
 Когда неизменяемый элемент передается в качестве аргумента, процедура не может изменить его в вызывающем коде независимо от того, был ли он передан `ByVal` или `ByRef`.  
  
 В случае изменяемого элемента см. таблицу, отображающую связь между типом элемента и механизмом передачи.  
  
|Тип элемента|Передача `ByVal`|Передача `ByRef`|  
|------------------|----------------------|----------------------|  
|Тип значения \(содержит только значение\)|Процедура не может изменять переменную или ее члены.|Процедура может изменять переменную и ее члены.|  
|Ссылочный тип \(содержит указатель на экземпляр класса или структуры\)|Процедура не может изменить переменную, но может изменять члены указываемого экземпляра.|Процедура может изменять переменную и члены указываемого экземпляра.|  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Различия между аргументами Modifiable и Nonmodifiable](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Практическое руководство. Изменение значения аргумента процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство. Защита аргумента процедуры от изменения значения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Практическое руководство. Принудительная передача аргумента по значению](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)