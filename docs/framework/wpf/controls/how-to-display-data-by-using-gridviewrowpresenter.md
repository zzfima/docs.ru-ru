---
title: "Практическое руководство. Отображение данных с помощью GridViewRowPresenter | Microsoft Docs"
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
  - "отображение данных с помощью элемента управления GridViewRowPresenter"
  - "GridViewRowPresenter"
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Отображение данных с помощью GridViewRowPresenter
В этом примере описывается порядок использования объектов <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> для отображения данных в столбцах.  
  
## Пример  
 В следующем примере описывается порядок определения объекта <xref:System.Windows.Controls.GridViewColumnCollection>, который используется для отображения свойств <xref:System.DateTime.DayOfWeek%2A> и <xref:System.DateTime.Year%2A> объекта <xref:System.DateTime> с помощью объектов <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter>.  В примере также определяется объект <xref:System.Windows.Style> для свойства <xref:System.Windows.Controls.GridViewColumn.Header%2A> элемента <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## См. также  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewColumnCollection>   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)