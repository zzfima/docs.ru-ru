---
title: "Общие сведения о компоненте SaveFileDialog (Windows Forms) | Microsoft Docs"
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
  - "SaveFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "диалоговое окно сохранения файлов, отображение"
  - "SaveFileDialog - компонент, сведения о SaveFileDialog"
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения о компоненте SaveFileDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.SaveFileDialog> является стандартным диалоговым окном.  Он аналогичен стандартному диалоговому окну **Сохранение файла**, используемому в операционных системах Windows.  Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.  
  
## Использование компонента SaveFileDialog  
 Компонент используется в качестве простого решения для сохранения файлов пользователями вместо диалогового окна, настраиваемого самостоятельно.  Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.  Однако следует помнить, что при использовании компонента <xref:System.Windows.Forms.SaveFileDialog> необходимо разработать собственный алгоритм сохранения файла.  
  
 Можно использовать метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна во время выполнения.  Используя метод <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>, можно открыть файл в режиме "чтение и запись".  
  
 Добавленный в форму компонент <xref:System.Windows.Forms.SaveFileDialog> появляется в нижней области конструктора Windows Forms.  
  
## См. также  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [Компонент SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)