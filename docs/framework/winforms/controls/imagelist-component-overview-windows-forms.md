---
title: "Общие сведения о компоненте ImageList (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ImageList"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления коллекцией, изображения"
  - "элемент управления списком значков"
  - "ImageList - компонент [Windows Forms], сведения о компоненте ImageList"
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Общие сведения о компоненте ImageList (Windows Forms)
Компонент <xref:System.Windows.Forms.ImageList> в Windows Forms используется для хранения изображений, которые затем будут отображаться элементами управления.  Список изображений позволяет написать код для создания единого согласованного каталога изображений.  Например, можно поворачивать изображения, отображаемые элементом управления <xref:System.Windows.Forms.Button>, просто изменив свойство <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> или <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> кнопки.  Кроме того, можно связать один список изображений с несколькими элементами управления.  Например, если вы используете оба элемента управления, <xref:System.Windows.Forms.ListView> и <xref:System.Windows.Forms.TreeView>, для отображения одного списка файлов, при изменении значка файла в списке изображений новый значок будет отображаться в обоих представлениях.  
  
## Использование компонента ImageList с элементами управления  
 Список изображений можно использовать с любым элементом управления, который имеет свойство `ImageList` \(или свойства <xref:System.Windows.Forms.ListView.SmallImageList%2A> и <xref:System.Windows.Forms.ListView.LargeImageList%2A>, если используется элемент управления <xref:System.Windows.Forms.ListView>\).  Элементы управления, которые могут быть связаны со списком изображений, включают: <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.Label>.  Чтобы связать список изображений с элементом управления, задайте для свойства `ImageList` элемента управления имя компонента <xref:System.Windows.Forms.ImageList>.  
  
## Основные свойства  
 Основным свойством компонента <xref:System.Windows.Forms.ImageList> является <xref:System.Windows.Forms.ImageList.Images%2A>, которое содержит изображения для использования связанным элементом управления.  Доступ к каждому отдельному изображению может осуществляться по значению индекса или ключу.  Свойство <xref:System.Windows.Forms.ImageList.ColorDepth%2A> определяет количество цветов, которые используются для отрисовки изображений.  Размер всех отображаемых изображений будет одинаковым \(задается свойством <xref:System.Windows.Forms.ImageList.ImageSize%2A>\).  Изображения, размер которых больше заданного, масштабируются.  
  
 При использовании [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] вы получаете доступ к большой библиотеке стандартных изображений, которые можно использовать в приложениях.  
  
## См. также  
 <xref:System.Windows.Forms.ImageList>   
 [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)