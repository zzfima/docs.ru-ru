---
title: "Объектные переменные в Visual Basic | Microsoft Docs"
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
  - "объектные переменные"
  - "объектные переменные, сведения о переменных объекта"
  - "объекты [Visual Basic], доступ"
  - "переменные [Visual Basic], объект"
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Объектные переменные в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Кроме того, что переменные могут хранить значения, они могут также ссылаться на объект.  Объект присваивается переменной по тем же причинам, по которым переменным присваиваются значения:  
  
-   Имя переменной, как правило, короче и легче запоминается, чем полный путь, содержащий методы и свойства, необходимые для доступа к самому объекту.  
  
-   Использование переменной, ссылающейся на объект, более эффективно, чем повторяющееся обращение к самому объекту с помощью необходимых методов или свойств.  
  
-   Переменную можно изменить для ссылки на другие объекты во время выполнения приложения.  
  
## Уменьшение размера кода  
 Можно использовать объектные переменные для сокращения вводимого кода.  В следующем примере используется полный путь, содержащий свойства и методы, необходимые для доступа к объекту <xref:System.Windows.Forms.Control>.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Этот код можно сократить и ускорить его выполнение с помощью объектной переменной.  Эту объектную переменную необходимо объявить в определенном классе, которому требуется ее присвоить \(в данном случае — `Control` \).  После того, как объект был присвоен переменной, с ней можно работать точно также, как с объектом, на который она ссылается.  Можно задать или извлечь свойства объекта или использовать любой из его методов.  В следующем примере используется объектная переменная для упрощения кода предыдущего примера.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## См. также  
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)