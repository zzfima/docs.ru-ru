---
title: "Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic) | Microsoft Docs"
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
  - "LinkLabel1_LinkClicked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], LinkLabel - элемент управления"
  - "связывание, к веб-страницам от форм"
  - "LinkLabel - элемент управления [Windows Forms], примеры"
  - "веб-страницы, отображение"
  - "Windows Forms, создание связи с веб-страницей"
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic)
Этот пример отображает веб\-страницу в браузере по умолчанию, если пользователь нажимает элемент управления Windows Forms <xref:System.Windows.Forms.LinkLabel>.  
  
## Пример  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Форма Windows Forms с именем `Form1`.  
  
-   Элемент управления <xref:System.Windows.Forms.LinkLabel> с именем `LinkLabel1`.  
  
-   Активное подключение к Интернету.  
  
## Безопасность платформы .NET Framework  
 Обращение к методу <xref:System.Diagnostics.Process.Start%2A> требует полного доверия.  Дополнительные сведения см. в разделе <xref:System.Security.SecurityException>.  
  
## См. также  
 <xref:System.Windows.Forms.LinkLabel>   
 [Элемент управления LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)