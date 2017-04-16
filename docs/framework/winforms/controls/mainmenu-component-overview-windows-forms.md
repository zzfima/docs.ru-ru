---
title: "Общие сведения о компоненте MainMenu (Windows Forms) | Microsoft Docs"
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
  - "MenuItem"
  - "MainMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MainMenu - элемент управления [Windows Forms], сведения об элементе управления MainMenu"
  - "меню"
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения о компоненте MainMenu (Windows Forms)
> [!IMPORTANT]
>  Хотя элементы управления <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменяют элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> предыдущих версий и расширяют их функциональные возможности, при необходимости элементы управления <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем.  
  
 Компонент форм Windows Forms <xref:System.Windows.Forms.MainMenu> отображает меню во время выполнения.  Все вложенные меню главного меню и отдельные пункты являются объектами <xref:System.Windows.Forms.MenuItem>.  
  
## Ключевые свойства  
 Пункт меню может быть назначен пунктом по умолчанию путем задания значения `true` для свойства <xref:System.Windows.Forms.MenuItem.DefaultItem%2A>.  При выборе данного меню пункт по умолчанию будет отображен полужирным шрифтом.  Для свойства <xref:System.Windows.Forms.MenuItem.Checked%2A> пункта меню может использоваться значение `true` или `false`, которое указывает, выбран ли данный пункт меню.  Значение свойства <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> определяет внешний вид выбранного пункта меню: если для свойства <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> задано значение `true`, рядом с пунктом появляется переключатель; если для свойства <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> задано значение `false`, рядом с пунктом появляется флажок.  
  
## См. также  
 <xref:System.Windows.Forms.MainMenu>   
 <xref:System.Windows.Forms.Menu>   
 <xref:System.Windows.Forms.MenuItem>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)