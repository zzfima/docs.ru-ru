---
title: "Практическое руководство. Создание свойства (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "процедуры, определение"
  - "свойства [Visual Basic]"
  - "код Visual Basic, процедуры"
  - "код Visual Basic, свойства"
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание свойства (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Заключите определение свойства между оператором `Property` и оператором `End Property`.  В этом определении вы определяете процедуру `Get`, `Set` или обе.  Весь код свойства находится в этих процедурах.  
  
 Процедура `Get` получает значение свойства, а процедура `Set` сохраняет значение.  Если требуется свойство, для которого есть права чтения и записи, необходимо определить обе процедуры.  Для свойства, доступного только для чтения, нужно определить только `Get`, а для свойства, доступного только для записи, определите только `Set`.  
  
### Создание свойства  
  
1.  Вне любых свойств и процедур используйте оператор [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md), за которым следует оператор `End Property`.  
  
2.  Если свойство принимает параметры, дополните ключевое слово `Property` именем процедуры, а затем списком параметров в круглых скобках.  
  
3.  После круглых скобок используйте оператор `As` для указания типа данных значения свойства.  Необходимо указать тип данных даже для свойства, доступного только для чтения.  
  
4.  Добавьте процедуры `Get` или `Set` нужным образом.  См. следующие объявления.  
  
### Создание процедуры Get, которая получает значение свойства  
  
1.  Между операторами `Property` и `End Property` добавьте [Оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md), за которым следует оператор `End Get`.  Для процедуры `Get` определять параметры необязательно.  
  
2.  Чтобы извлечь значение свойства, поместите операторы кода между операторами `Get` и `End Get`.  Этот код может включать другие вычисления и манипуляции с данными в дополнение к созданию и возврату значения свойства.  
  
3.  Оператор `Return` используется для возвращения значения свойства в вызывающий код.  
  
 Необходимо написать процедуру `Get` для свойства чтения и записи и для свойства только для чтения.  Определять `Get` для свойства, доступного только для записи, не нужно.  
  
### Создание процедуры Set, которая записывает значение свойства  
  
1.  Между операторами `Property` и `End Property` добавьте [Оператор Set](../../../../visual-basic/language-reference/statements/set-statement.md), за которым следует оператор `End Set`.  
  
2.  В операторе `Set` после ключевого слова `Set` укажите список параметров в круглых скобках.  Этот список параметров должен включать, по крайней мере, параметр для значения, предаваемого вызывающим кодом.  Имя этого параметра по умолчанию — `Value`, но при необходимости можно использовать другое имя.  Параметр значения должен быть того же типа, что и само свойство.  
  
3.  Поместите операторы кода для получения значения свойства между операторами `Set` и `End Set`.  Этот код может включать другие вычисления и манипуляции с данными в дополнение к созданию и возврату значений свойств.  
  
4.  Используйте параметр значения, чтобы принять значение, предоставленное вызывающим кодом.  Можно либо хранить это значение непосредственно в операторе присваивания, или использовать его в выражении для вычисления внутреннего значения.  
  
 Необходимо написать процедуру `Set` для свойства чтения и записи и для свойства, доступного только для записи.  Определять процедуру `Set` для свойства, доступного только для записи, не нужно.  
  
## Пример  
 В следующем примере создается свойство чтения\/записи, которое сохраняет полное имя как два составных имени — имя и фамилия.  Когда вызывающий код считывает процедуры `fullName`, процедура `Get` объединяет два составных имени и возвращает полное имя.  Когда вызывающий код присваивает новое полное имя, процедура `Set` пытается разделить его на два составных имени.  Если не удается найти пробел, то она сохраняет все полное имя как имя.  
  
 [!code-vb[VbVbcnProcedures#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 В следующем примере показаны вызовы процедур свойств из `fullName`.  Первый вызов задает значение свойства, а второй вызов извлекает его.  
  
 [!code-vb[VbVbcnProcedures#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Практическое руководство. Вызов процедуры свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство. Запись значения в свойство](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Практическое руководство. Получение значения из свойства](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)