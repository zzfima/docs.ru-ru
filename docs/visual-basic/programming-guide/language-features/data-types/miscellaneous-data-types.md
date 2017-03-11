---
title: "Прочие типы данных (Visual Basic) | Microsoft Docs"
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
  - "типы данных [Visual Basic], выбор"
  - "Object - тип данных, типы данных"
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Прочие типы данных (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] имеется несколько типов данных, непредназначенных для чисел или символов.  Они предусмотрены для специализированных данных, например для значений "да"\-"нет", даты\-времени и адресов объектов.  
  
 Таблицу, в которой приведено сравнение типов данных [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], см. в разделе [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Логический тип  
 [Тип данных Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) является значением без знака, интерпретируется как `True` или `False`.  Размер его строки данных зависит от платформы для которой он реализуется.  Если переменная может содержать только два значения состояния, например true\/false, yes\/no или on\/off, объявите ее в качестве `Boolean`.  
  
## Тип даты  
 [Тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) является 64\-разрядным значением, содержащим сведения о дате и времени.  Каждое приращение представляет интервал времени в 100 наносекунд, начиная с 00:00 1\-го января 1\-го года по григорианскому календарю.  Если переменная может содержать значение даты, значение времени, или оба этих значения, объявите ее в качестве `Date`.  
  
## Тип объекта  
 Тип данных [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) является 32\-битным адресом, указывающим на экземпляр объекта в приложении пользователя или в каком\-либо другом приложении.  Переменная `Object` может указывать на любой объект, распознаваемый приложением, а также на данные любого типа данных.  К ним относятся и типы значенийкак `Integer`"  `Boolean`и экземпляров структуры и ссылочные типы, созданный из классов как экземпляры объектов  `String` и  <xref:System.Windows.Forms.Form>и экземпляры массива.  
  
 Если переменная хранит указатель на экземпляр класса, который не известен во время компиляции, или она может указывать на данные различных типов данных, объявите ее в качестве `Object`.  
  
 Преимущество  `Object` тип данных, который можно использовать для хранения данных любого типа данных.  Недостатком являются дополнительные операции, большее количество времени для выполнения и снижение производительности приложения.  Если переменная `Object` используется для типов значений, вызываются *упаковка* и *распаковка*.  Если она используется для ссылочных типов, вызывается *позднее связывание*.  
  
## См. также  
 [Символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Символьные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)