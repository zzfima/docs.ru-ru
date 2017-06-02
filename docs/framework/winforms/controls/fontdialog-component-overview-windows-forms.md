---
title: "Общие сведения о компоненте FontDialog (Windows Forms) | Microsoft Docs"
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
  - "FontDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "диалоговое окно шрифтов"
  - "диалоговое окно шрифтов, Windows Forms"
  - "FontDialog - компонент [Windows Forms], сведения о компоненте FontDialog"
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения о компоненте FontDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.FontDialog> является стандартным диалоговым окном, аналогичным окну Windows **Шрифт**; он используется для предоставления шрифтов, установленных в операционной системе.  Этот компонент используется в приложении Windows в качестве простого решения для выбора шрифтов вместо диалогового окна, настраиваемого самостоятельно.  
  
 По умолчанию в диалоговом окне отображаются списки "Шрифт", "Стиль" и "Размер"; поля флажков для таких эффектов, как зачеркивание и подчеркивание; раскрывающийся список "Набор символов"; поле, в котором показан образец шрифта.  \(Набор символов определяет, какие символы доступны для данного шрифта: например, иврит или японский.\) Чтобы вывести диалоговое окно шрифтов, следует вызвать метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## Ключевые свойства  
 Этот компонент обладает рядом свойств, определяющих его внешний вид.  Свойствами, задающими параметры диалогового окна, являются <xref:System.Windows.Forms.FontDialog.Font%2A> и <xref:System.Windows.Forms.FontDialog.Color%2A>.  Свойство <xref:System.Windows.Forms.FontDialog.Font%2A> задает шрифт, стиль, размер, набор символов и эффекты, например:  `Arial, 10pt, style=Italic, Strikeout`.  
  
## См. также  
 <xref:System.Windows.Forms.FontDialog>   
 [Компонент FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)