---
title: "Общие сведения об элементе управления MenuStrip (Windows Forms) | Microsoft Docs"
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
  - "MenuStrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "меню, создание"
  - "MenuStrip - элемент управления [Windows Forms], сведения об элементе управления MenuStrip"
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения об элементе управления MenuStrip (Windows Forms)
Меню служат для размещения логически сгруппированных команд.  
  
 Элемент управления <xref:System.Windows.Forms.MenuStrip> появился в этой версии Visual Studio и .NET Framework.  С помощью него можно создавать меню, аналогичные меню Microsoft Office.  
  
 Элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает интерфейс MDI, слияние меню, всплывающие подсказки и переполнение.  Удобство использования меню можно повысить, добавив в них клавиши быстрого доступа, сочетания клавиш, флажки, значки и разделители.  
  
 Элемент управления <xref:System.Windows.Forms.MenuStrip> заменяет элемент управления <xref:System.Windows.Forms.MainMenu> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.MainMenu> можно сохранить для обратной совместимости и использования в будущем.  
  
## Способы использования элемента управления MenuStrip  
 Элемент управления <xref:System.Windows.Forms.MenuStrip> может использоваться в следующих целях.  
  
-   Создание легко настраиваемых, стандартных меню, поддерживающих широкий набор возможностей компоновки и пользовательского интерфейса, таких как упорядочение и выравнивание текста и изображений, операции перетаскивания, интерфейс MDI, переполнение и альтернативные режимы доступа к пунктам меню.  
  
-   Поддержка типового вида и поведения операционной системы.  
  
-   Согласованная обработка событий для всех контейнеров и содержащихся в них элементов аналогично обработке событий для других элементов управления.  
  
 В следующей таблице показаны некоторые особо важные свойства элемента управления <xref:System.Windows.Forms.MenuStrip> и связанных с ним классов.  
  
|Свойство.|Описание|  
|---------------|--------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Получает или задает объект <xref:System.Windows.Forms.ToolStripMenuItem>, используемый для отображения списка дочерних форм MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=fullName>|Получает или задает способ слияния дочерних меню с родительскими меню в приложениях MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=fullName>|Получает или задает положение пункта меню при слиянии меню в приложениях MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=fullName>|Получает или задает значение, определяющее, является ли форма контейнером для дочерних форм MDI.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Получает или задает значение, определяющее, должны ли отображаться всплывающие подсказки для элемента управления <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Получает или задает значение, определяющее, поддерживает ли элемент управления <xref:System.Windows.Forms.MenuStrip> функцию переполнения.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Получает или задает сочетания клавиш, связанные с элементом <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Получает или задает значение, определяющее, будет ли сочетание клавиш, связанное с данным элементом <xref:System.Windows.Forms.ToolStripMenuItem>, отображаться рядом с элементом <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 В следующей таблице приведены основные сопутствующие классы элемента управления <xref:System.Windows.Forms.MenuStrip>.  
  
|Класс|Описание|  
|-----------|--------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Представляет доступный для выбора параметр, отображаемый в объекте <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Представляет контекстное меню.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Представляет элемент управления, позволяющий пользователю выбрать один элемент из списка, отображаемого при щелчке мышью по кнопке <xref:System.Windows.Forms.ToolStripDropDownButton> или пункту меню более высокого уровня.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Обеспечивает базовую функциональность для элементов управления, производных от <xref:System.Windows.Forms.ToolStripItem>, служащих для отображения раскрывающихся списков при щелчке мышью.|  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>