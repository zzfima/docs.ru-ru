---
title: "Общие сведения о компоненте PageSetupDialog (Windows Forms) | Microsoft Docs"
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
  - "PageSetupDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Параметры страницы - диалоговое окно, отображение"
  - "PageSetupDialog - компонент"
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения о компоненте PageSetupDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.PageSetupDialog> является стандартным диалоговым окном, используемым для задания сведений о странице для печати в приложениях Windows.  Этот компонент используется в приложении Windows в качестве простого решения для задания параметров настройки страницы вместо диалогового окна, настраиваемого самостоятельно.  Можно разрешить пользователям задавать параметры границ и полей, верхних и нижних колонтитулов, а также выбирать книжную или альбомную ориентацию.  Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.  
  
## Ключевые свойства и методы  
 Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна во время выполнения.  Этот компонент имеет настраиваемые свойства, относящиеся либо к отдельной странице \(класс <xref:System.Drawing.Printing.PrintDocument>\), либо к любому документу \(класс <xref:System.Drawing.Printing.PageSettings>\).  Кроме того, с помощью компонента <xref:System.Windows.Forms.PageSetupDialog> можно определить параметры определенного принтера, хранящиеся в классе <xref:System.Drawing.Printing.PrinterSettings>.  
  
 Добавленный в форму компонент <xref:System.Windows.Forms.PageSetupDialog> появляется в нижней области конструктора Windows Forms.  
  
## См. также  
 <xref:System.Windows.Forms.PageSetupDialog>   
 [Компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)