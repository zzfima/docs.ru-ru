---
title: "Различия между аргументами Modifiable и Nonmodifiable (Visual Basic) | Microsoft Docs"
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
  - "аргументы [Visual Basic], изменяемый"
  - "аргументы [Visual Basic], неизменяемый"
  - "аргументы процедур"
  - "процедуры, аргументы"
  - "код Visual Basic, процедуры"
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

При вызове процедуры, как правило, ей передается один или несколько аргументов.  Каждый аргумент соответствует базовому элементу программирования.  Базовые элементы и аргументы сами могут быть либо изменяемыми либо неизменяемыми.  
  
## Изменяемые и неизменяемые элементы  
 Элемент программирования может быть *изменяемым элементом \(modifiable element\)*, значение которого может быть изменено, или *неизменяемым элементом \(nonmodifiable element\)*, который имеет фиксированное значение после его создания.  
  
 В следующей таблице перечислены изменяемые и неизменяемые элементы программирования.  
  
|Изменяемые элементы|Неизменяемые элементы|  
|-------------------------|---------------------------|  
|Локальные переменные \(объявленные внутри процедур\), включая переменные объектов, за исключением доступных только для чтения|Переменные, поля и свойства доступные только для чтения|  
|Поля \(переменные\-члены модулей, классов и структур\) доступные только для чтения|Константы и литералы|  
|Свойства, за исключением доступных только для чтения|Члены перечисления|  
|Элементы массива|Выражения \(даже если их элементы являются изменяемыми\)|  
  
## Изменяемые и неизменяемые аргументы  
 *modifiable argument* является изменяемым базовым элементом.  Код вызова может хранить новое значение в любое время, и если передать аргумент [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), то код в процедуре сможет изменить базовый элемент в коде вызова.  
  
 *nonmodifiable argument* имеет неизменяемый основной элемент или передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  Процедура не может изменить базовый элемент в коде вызова, даже если он является изменяемым элементом.  Если это неизменяемый элемент, код вызова сам не может изменить его.  
  
 Вызванная процедура может изменить локальную копию неизменяемого аргумента, но это изменение не затронет базовый элемент в вызывающем коде.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Различия между передачей аргумента по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Практическое руководство. Изменение значения аргумента процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство. Защита аргумента процедуры от изменения значения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Практическое руководство. Принудительная передача аргумента по значению](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)