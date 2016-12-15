---
title: "Присваивание объектных переменных (Visual Basic) | Microsoft Docs"
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
  - "операторы назначения, присваивание объектных переменных"
  - "текущий экземпляр, определенный"
  - "Me - ключевое слово, в качестве переменной объекта"
  - "Nothing - ключевое слово, присваивание объектных переменных"
  - "объектные переменные, назначение"
  - "объектные переменные, инициализация"
  - "объекты [Visual Basic], текущий экземпляр"
  - "переменные [Visual Basic], назначение"
  - "переменные [Visual Basic], инициализация"
  - "переменные [Visual Basic], объектные переменные"
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Присваивание объектных переменных (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Для присвоения объекта переменной используется обычный оператор присваивания.  Можно присвоить объектное выражение или ключевое слово [Nothing](../../../../visual-basic/language-reference/nothing.md), как показано в следующем примере.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` означает, что ни один объект не присвоен этой переменной в данный момент.  
  
## Инициализация  
 При запуске кода объектные переменные инициализируются значением `Nothing`.  Те, чьи объявления содержат инициализацию, повторно инициализируются значениями, указанными при выполнении инструкций объявления.  
  
 Можно включить инициализацию в объявление с помощью ключевого слова [New](../../../../visual-basic/language-reference/operators/new-operator.md).  Приведенные ниже операторы объявления объявляют переменные объекта `testUri` и `ver` и присваивают им определенные объекты.  Каждый использует один из перегруженных конструкторов соответствующего класса для инициализации объекта.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## Отсоединение  
 Задание для переменной объекта значения `Nothing` разрывает связь переменной с конкретным объектом.  Это предотвращает случайное изменение объекта при изменении переменной.  Это также позволяет проверить, содержит ли переменная ссылку на допустимый объект, как показано в следующем примере.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Если объект, на который ссылается переменная, находится в другом приложении, такая проверка не позволит определить, закрыто ли данное приложение или оно просто пометило объект как недействительный.  
  
 Переменная объекта со значением `Nothing` также называется *пустой ссылкой*.  
  
## Текущий экземпляр  
 *Текущим экземпляром* объекта называется экземпляр, в котором выполняется код в данный момент времени.  Поскольку весь код выполняется внутри процедуры, текущим экземпляром является тот, в котором вызвана процедура.  
  
 Ключевое слово `Me` выполняет функции переменной объекта, ссылаясь на текущий экземпляр.  Если процедура не является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), она может использовать ключевое слово `Me` для получения указателя на текущий экземпляр.  Общие процедуры не могут быть связаны с определенным экземпляром класса.  
  
 Использование `Me` особенно удобно для передачи текущего экземпляра процедуре другого модуля.  Например, пусть имеется множество XML\-документов и во все эти документы требуется добавить некоторый стандартный текст.  В следующем примере определяется процедура для этого.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Каждый объект XML\-документа может затем вызвать процедуру и передать свой текущий экземпляр в качестве аргумента.  Это показано в приведенном ниже примере.  
  
```  
addStandardText(Me)  
```  
  
## См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)