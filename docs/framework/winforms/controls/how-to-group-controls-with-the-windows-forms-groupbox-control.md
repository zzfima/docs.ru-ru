---
title: "Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], группирование"
  - "GroupBox - элемент управления [Windows Forms], группирование элементов управления"
  - "элементы управления Windows Forms, группирование"
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms
Элементы управления Windows Forms <xref:System.Windows.Forms.GroupBox> используются для группировки других элементов управления.  Существуют три причины для группировки элементов управления.  
  
-   Создание наглядной группировки взаимосвязанных элементов формы для формирования более понятного пользовательского интерфейса.  
  
-   Создание программной группировки \(например, переключателей\).  
  
-   Перемещение элементов управления как одного объекта во время проектирования.  
  
### Чтобы создать группу элементов управления, выполните следующие действия:  
  
1.  Нарисуйте элемент управления <xref:System.Windows.Forms.GroupBox> в форме.  
  
2.  Добавьте другие элементы управления в группу путем рисования каждого элемента внутри группы.  
  
     Если надо включить в группу уже существующие элементы управления, можно выделить все элементы управления, вырезать их в буфер обмена, выбрать элемент управления <xref:System.Windows.Forms.GroupBox> и затем вставить их в группу.  Также можно перетащить их в группу.  
  
3.  Установите с помощью значения свойства <xref:System.Windows.Forms.GroupBox.Text%2A> группы нужный заголовок.  
  
## См. также  
 <xref:System.Windows.Forms.GroupBox>   
 [Элемент управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)