---
title: "Общие сведения о стилях заголовков столбцов GridView и шаблонах | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "заголовки столбцов, настройка"
  - "элементы управления, ListView"
  - "GridView - режим представления, настройка заголовков столбцов"
  - "верхние колонтитулы, настройка"
  - "ListView - элементы управления [WPF], стили заголовков столбцов GridView"
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения о стилях заголовков столбцов GridView и шаблонах
Этот обзор описывает порядок приоритетов для свойств, предназначенных для настройки заголовков столбцов в режиме представления <xref:System.Windows.Controls.GridView> элемента управления <xref:System.Windows.Controls.ListView>.  
  
## Настройка заголовка столбца в GridView  
 Свойства, определяющие содержимое, макет и стиль заголовка столбца в <xref:System.Windows.Controls.GridView>, присутствуют во многих связанных классах.  Некоторые из этих свойств содержат похожие или аналогичные функции.  
  
 В следующей таблице показаны группы свойств, которые выполняют одну и ту же функцию.  Можно использовать эти свойства для настройки заголовков столбцов в <xref:System.Windows.Controls.GridView>.  Порядок приоритетов для связанных свойств определяется справа налево, наивысший приоритет имеет свойство в крайнем правом столбце.  Например, если <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> задано для объекта <xref:System.Windows.Controls.GridViewColumnHeader>, а <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> задано для связанного объекта <xref:System.Windows.Controls.GridViewColumn>, то <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> имеет более высокий приоритет.  В этом случае <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> не оказывает влияния.  
  
 **Связанные свойства для заголовков столбцов в GridView**  
  
|||||  
|-|-|-|-|  
|**Классы**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Свойства контекстного меню**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|Неприменимо|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**Подсказка**<br /><br /> **Свойства**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|Неприменимо|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Шаблон заголовка**<br /><br /> **Свойства**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Свойства стилей**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup> Для **свойств шаблона заголовка**, если заданы свойства шаблона и селектора шаблона, то свойство шаблона имеет приоритет.  Например, если заданы оба свойства <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>, приоритет имеет свойство <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.  
  
## См. также  
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)