---
title: "Общие сведения о компоненте FolderBrowserDialog (Windows Forms) | Microsoft Docs"
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
  - "FolderBrowserDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "каталоги [Windows Forms], включение просмотра в приложениях"
  - "FolderBrowserDialog - компонент [Windows Forms], сведения о FolderBrowserDialog"
  - "папки [Windows Forms], включение просмотра в приложениях"
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения о компоненте FolderBrowserDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> является модальным диалоговым окном, предназначенным для перехода к папкам и их выбора.  В рамках компонента <xref:System.Windows.Forms.FolderBrowserDialog> также могут быть созданы новые папки.  
  
> [!NOTE]
>  Для выбора вместо папок файлов используйте компонент [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md).  
  
 Компонент <xref:System.Windows.Forms.FolderBrowserDialog> отображается во время выполнения с использованием метода <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  Для определения папок самого верхнего уровня и любых папок нижележащих уровней, которые будут отображаться в дереве этого диалогового окна, задайте свойство <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>.  После отображения этого диалогового окна свойство <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> можно использовать для получения пути к выбранной папке.  
  
 Добавленный в форму компонент <xref:System.Windows.Forms.FolderBrowserDialog> появляется в нижней области конструктора Windows Forms.  
  
## См. также  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)   
 [Компонент FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)