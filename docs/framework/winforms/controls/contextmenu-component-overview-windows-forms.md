---
title: "Общие сведения о компоненте ContextMenu (Windows Forms) | Microsoft Docs"
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
  - "ContextMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "контекстные меню, компонент ContextMenu"
  - "ContextMenu - компонент [Windows Forms], сведения о компоненте ContextMenu"
  - "контекстные меню, компонент ContextMenu"
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Общие сведения о компоненте ContextMenu (Windows Forms)
> [!IMPORTANT]
>  Хотя элементы управления <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменяют элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> предыдущих версий и расширяют их функциональные возможности, при необходимости элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем.  
  
 Компонент Windows Forms <xref:System.Windows.Forms.ContextMenu> используется для предоставления пользователям доступного контекстного меню часто используемых команд, связанных с выделенным объектом.  Элементы контекстного меню часто представляют собой группы элементов из основных меню, встречающихся в различных местах приложения.  Доступ к контекстному меню обычно осуществляется путем нажатия правой кнопки мыши.  В формах Windows Forms контекстные меню связаны с элементами управления.  
  
## Ключевые свойства  
 Связь контекстного меню с элементом управления создается путем задания для свойства <xref:System.Windows.Forms.Control.ContextMenu%2A> элемента управления компонента <xref:System.Windows.Forms.ContextMenu>.  Одно контекстное меню можно связать с несколькими элементами управления, но каждому элементу управления должно соответствовать только одно контекстное меню.  
  
 Ключевым свойством компонента <xref:System.Windows.Forms.ContextMenu> является свойство <xref:System.Windows.Forms.Menu.MenuItems%2A>.  Добавление пунктов меню может производиться путем программного создания объектов <xref:System.Windows.Forms.MenuItem> и добавления их в свойство <xref:System.Windows.Forms.Menu.MenuItemCollection> контекстного меню.  Поскольку элементы контекстного меню обычно заимствуются из других меню, чаще всего они добавляются в контекстное меню путем копирования.  
  
## См. также  
 <xref:System.Windows.Forms.ContextMenu>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>