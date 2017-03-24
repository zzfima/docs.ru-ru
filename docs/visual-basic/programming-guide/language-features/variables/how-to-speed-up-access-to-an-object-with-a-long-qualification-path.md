---
title: "Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объектные переменные, доступ"
  - "переменные [Visual Basic], доступ"
  - "переменные [Visual Basic], объект"
  - "With - блок"
  - "With - оператор"
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если необходим частый доступ к объекту, классификационный путь которого требует применения нескольких методов и свойств, то можно ускорить код, не повторяя классификационный путь.  
  
 Для того, чтобы избежать повторение классификационного пути, существуют два способа.  Можно назначить объект переменной, или можно использовать его в блоке `With`... `End With`.  
  
### Ускорение доступа к сильно классифицированному объекту присвоением ему переменной  
  
1.  Объявите переменную типа объекта, к которому часто необходим доступ.  Укажите классификационный путь в части инициализации объявления.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Используйте переменную для доступа к элементам объекта.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### Ускорение доступа к сильно классифицированному объекту с помощью блока With... End With  
  
1.  Поместите классификационный пусть в инструкцию `With`.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Обращайтесь к членам объекта внутри блока `With` перед инструкцией `End With`.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)