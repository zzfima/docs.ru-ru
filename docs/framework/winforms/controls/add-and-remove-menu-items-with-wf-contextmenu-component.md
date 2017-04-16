---
title: "Практическое руководство. Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "контекстные меню, добавление элементов"
  - "контекстные меню, примеры"
  - "контекстные меню, удаление элементов"
  - "ContextMenu - компонент [Windows Forms], добавление элементов"
  - "ContextMenu - компонент [Windows Forms], удаление элементов"
  - "примеры [Windows Forms], контекстные меню"
  - "контекстные меню, добавление элементов"
  - "контекстные меню, примеры"
  - "контекстные меню, удаление элементов"
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms
Описание способов добавления и удаления элементов контекстного меню в Windows Forms.  
  
 Компонент Windows Forms <xref:System.Windows.Forms.ContextMenu> предоставляет меню часто используемых команд, применимых к выделенному объекту.  В контекстное меню можно добавлять элементы, добавляя объекты <xref:System.Windows.Forms.MenuItem> в коллекцию <xref:System.Windows.Forms.Menu.MenuItems%2A>.  
  
 Элементы контекстного меню можно удалять без возможности восстановления; однако во время выполнения более целесообразным может оказаться скрытие или отключение элементов.  
  
> [!IMPORTANT]
>  Хотя элементы управления <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменяют элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> предыдущих версий и расширяют их функциональные возможности, при необходимости элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем.  
  
### Удаление элементов из контекстного меню  
  
1.  Для удаления определенного элемента меню воспользуйтесь методом <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> или <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> коллекции <xref:System.Windows.Forms.Menu.MenuItems%2A> компонента <xref:System.Windows.Forms.ContextMenu>.  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     \-или\-  
  
2.  Для удаления всех элементов меню воспользуйтесь методом `Clear` коллекции `MenuItems` компонента <xref:System.Windows.Forms.ContextMenu>.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ContextMenu>   
 [Компонент ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)   
 [Общие сведения об элементе управления ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)