---
title: "Общие сведения об элементе управления LinkLabel (Windows Forms) | Microsoft Docs"
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
  - "LinkLabel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Label - элемент управления [Windows Forms], об элементе управления Label"
  - "LinkLabel - элемент управления [Windows Forms], сведения об элементе управления LinkLabel"
  - "связи, LinkLabel - элемент управления"
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения об элементе управления LinkLabel (Windows Forms)
Элемент управления форм <xref:System.Windows.Forms.LinkLabel> позволяет добавлять ссылки в стиле веб в приложения форм Windows.  Элемент управления <xref:System.Windows.Forms.Label> может использоваться для тех же целей, что и элемент управления <xref:System.Windows.Forms.LinkLabel>; кроме того, имеется возможность задать часть текста в качестве ссылки на файл, папку или веб\-страницу.  
  
## Возможные действия с элементом управления LinkLabel  
 В дополнение ко всем свойствам, методам и событиям элемента управления <xref:System.Windows.Forms.LinkLabel>, у элемента управления <xref:System.Windows.Forms.Label> имеются еще свойства для гиперссылок и цвета ссылок.  Свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> определяет область текста, которая активирует ссылку.  Свойства <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> и <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> определяют цвета ссылки.  Событие <xref:System.Windows.Forms.LinkLabel.LinkClicked> определяет, что происходит при выборе текста ссылки.  
  
 Простейшее применение элемента управления <xref:System.Windows.Forms.LinkLabel> — отображение одиночной ссылки с использованием свойства <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, однако также возможно отображение нескольких гиперссылок с помощью свойства <xref:System.Windows.Forms.LinkLabel.Links%2A>.  Свойство <xref:System.Windows.Forms.LinkLabel.Links%2A> позволяет получить доступ к коллекции ссылок.  Кроме того, в свойстве <xref:System.Windows.Forms.LinkLabel.Link> можно определить данные для каждого отдельного объекта <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>.  Значение свойства <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> служит для хранения размещения отображаемого файла или адреса веб\-узла.  
  
## См. также  
 <xref:System.Windows.Forms.LinkLabel>   
 [Общие сведения об элементе управления Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Практическое руководство. Создание связи с объектом или веб\-страницей с помощью элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)