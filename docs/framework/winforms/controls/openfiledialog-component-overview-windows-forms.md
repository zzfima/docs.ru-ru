---
title: "Общие сведения о компоненте OpenFileDialog (Windows Forms) | Microsoft Docs"
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
  - "OpenFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Открыть файл - диалоговое окно, отображение в формах Windows Forms"
  - "OpenFileDialog - компонент, сведения об OpenFileDialog"
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения о компоненте OpenFileDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.OpenFileDialog> является стандартным диалоговым окном.  Он аналогичен диалоговому окну **Открыть файл** операционной системы Windows.  Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.  
  
## Использование компонента  
 Этот компонент используется в приложении Windows в качестве простого решения для выбора файлов вместо диалогового окна, настраиваемого самостоятельно.  Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.  Однако следует помнить, что при использовании компонента <xref:System.Windows.Forms.OpenFileDialog> необходимо разработать собственный алгоритм открытия файла.  
  
 Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна во время выполнения.  При помощи свойства <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> пользователям можно разрешить выбор нескольких файлов для открытия.  Кроме того, с помощью свойства <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> можно задать отображение в диалоговом окне флажка "Только для чтения".  Свойство <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> показывает, установлен ли флажок "доступно только для чтения".  Наконец, свойство <xref:System.Windows.Forms.FileDialog.Filter%2A> задает строку фильтра для текущего имени файла, которая определяет варианты, отображающиеся в поле "Тип файлов" диалогового окна.  
  
 Добавленный в форму компонент <xref:System.Windows.Forms.OpenFileDialog> появляется в нижней области конструктора Windows Forms.  
  
## См. также  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [Компонент OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)