---
title: "Общие сведения об элементе управления Splitter (Windows Forms) | Microsoft Docs"
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
  - "Splitter"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Splitter - элемент управления [Windows Forms], сведения об элементе управления Splitter"
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения об элементе управления Splitter (Windows Forms)
> [!IMPORTANT]
>  Хотя элемент управления <xref:System.Windows.Forms.SplitContainer> заменяет элемент управления <xref:System.Windows.Forms.Splitter> предыдущих версий и расширяет его функциональные возможности, однако при необходимости элемент управления <xref:System.Windows.Forms.Splitter> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элементы управления Windows Forms <xref:System.Windows.Forms.Splitter> \(разделители\) используются для изменения размеров закрепленных элементов управления во время выполнения.  Элемент управления <xref:System.Windows.Forms.Splitter> часто используется в формах с элементами управления, в которых представлены данные переменной длины, например в проводнике Windows, где области данных в разное время содержат сведения разных размеров.  
  
## Работа с элементом управления Splitter  
 Когда пользователь наводит указатель мыши на незакрепленный край элемента управления, размер которого допускает изменение при помощи разделителя, указатель принимает другой вид, показывая, что размер элемента управления можно изменять.  Разделитель позволяет пользователю изменить размер закрепленного элемента управления, находящегося непосредственно перед разделителем.  Таким образом, чтобы пользователь мог изменять размер закрепленного элемента управления во время выполнения, следует закрепить этот элемент управления у края контейнера, а затем закрепить разделитель у той же стороны этого контейнера.  
  
## См. также  
 <xref:System.Windows.Forms.SplitContainer>   
 [Практическое руководство. Закрепление элементов управления в формах Windows Forms.](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)