---
title: "Общие сведения о компоненте PrintDialog (Windows Forms) | Microsoft Docs"
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
  - "PrintDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Печать - диалоговое окно, отображение"
  - "PrintDialog - компонент [Windows Forms], сведения о компоненте PrintDialog"
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения о компоненте PrintDialog (Windows Forms)
Компонент форм Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) является стандартным диалоговым окном, используемым для выбора принтера и печатаемых страниц, а также для определения других параметров печати в приложениях Windows.  Он используется в качестве простого решения для выбора принтера и параметров печати вместо диалогового окна, настраиваемого самостоятельно.  Пользователям можно предоставить большой выбор варианта текста.  Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.  Компонент <xref:System.Windows.Forms.PrintDialog> наследуется от класса <xref:System.Windows.Forms.CommonDialog>.  
  
## Использование компонента  
 Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна во время выполнения.  Этот компонент имеет свойства, относящиеся либо к отдельному заданию печати \(класс <xref:System.Drawing.Printing.PrintDocument>\), либо к параметрам настройки отдельного принтера \(класс <xref:System.Drawing.Printing.PrinterSettings>\).  Любой из наборов свойств, в свою очередь, может применяться к нескольким принтерам.  
  
 Добавленный в форму компонент <xref:System.Windows.Forms.PrintDialog> появляется в нижней области конструктора Windows Forms.  
  
## См. также  
 <xref:System.Windows.Forms.PrintDialog>   
 [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)