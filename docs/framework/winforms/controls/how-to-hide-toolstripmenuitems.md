---
title: "Практическое руководство. Сокрытие объектов ToolStripMenuItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "скрытие пунктов меню"
  - "пункты меню, скрытие"
  - "меню, скрытие пунктов меню"
  - "MenuStrip - элемент управления [Windows Forms], скрытие пунктов меню"
  - "ToolStripMenuItem - элементы, скрытие"
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Сокрытие объектов ToolStripMenuItem
Скрытие пунктов меню позволяет управлять пользовательским интерфейсом приложения и ограничивать использование команд пользователями.  Во многих случаях, когда все пункты меню становятся недоступными, необходимо скрыть меню целиком.  Это позволит пользователю меньше отвлекаться.  Более того, можно одновременно скрыть и отключить меню или пункт меню, поскольку скрытие меню не запрещает доступ пользователя к командам меню с помощью сочетаний клавиш.  
  
### Скрытие элемента меню программными средствами  
  
-   В методе, который использовался для задания свойства элемента меню, добавьте код для присвоения свойству <xref:System.Windows.Forms.ToolStripItem.Visible%2A> значения `false`.  
  
    ```vb  
    MenuItem3.Visible = False  
  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)