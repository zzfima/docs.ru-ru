---
title: "Определение типа объекта (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "классы [Visual Basic], определение, к какому классу относится объект"
  - "объектные переменные, тестирование значений"
  - "объекты [Visual Basic], тип, определяющий"
  - "TypeName - функция"
  - "TypeOf...Is - выражение, тип объекта во время выполнения"
  - "типы [Visual Basic], определение типов объектов Visual Basic"
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Определение типа объекта (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Универсальные объектные переменные \(переменные, объявляемые как `Object`\) содержат объекты любого класса.  При использовании переменных типа `Object` может потребоваться предпринять различные действия в зависимости от класса объекта; например, некоторые объекты могут не поддерживать конкретное свойство или метод.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет два средства определения типа объекта, хранящегося в объектной переменной: функцию `TypeName` и оператор `TypeOf...Is`.  
  
## TypeOf…Is и TypeName  
 Функция `TypeName` возвращает строку. Эта функция наиболее удобна при необходимости сохранить или отобразить имя класса объекта, как показано в следующем фрагменте кода:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 Оператор `TypeOf...Is` наиболее удобен при проверке типа объекта, поскольку он работает намного быстрее, чем эквивалентная операция сравнения строк с помощью `TypeName`.  В следующем фрагменте кода используется `TypeOf...Is` внутри инструкции `If...Then...Else`:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 А теперь несколько слов предостережения.  Оператор `TypeOf...Is` возвращает `True`, если объект имеет конкретный тип или является производным от конкретного типа.  Почти все в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполняется с помощью объектов, содержащих некоторые элементы, которые не считаются обычно объектами, например строки и целые числа.  Эти объекты являются производными и наследуют методы от <xref:System.Object>.  При передаче `Integer` и вычислении с `Object` оператор `TypeOf...Is` возвращает `True`.  В следующем примере сообщается, что параметр `InParam` является и `Object`, и `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 В следующем примере используются и `TypeOf...Is`, и `TypeName` для определения типа объекта, переданного в аргументе `Ctrl`.  Процедура `TestObject` вызывает `ShowType` с тремя разными типами элементов управления.  
  
#### Для запуска примера  
  
1.  Создайте новый проект приложения Windows и добавьте элементы управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox> и <xref:System.Windows.Forms.RadioButton> на форму.  
  
2.  С помощью кнопки на форме вызовите процедуру `TestObject`.  
  
3.  Добавьте следующий код в форму:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>   
 [Вызов свойства или метода с помощью строкового имени](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Оператор If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)