---
title: "Практическое руководство. Сортировка и группировка данных с помощью представления в XAML | Microsoft Docs"
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
  - "привязка данных, группировка данных в представлениях XAML"
  - "привязка данных, сортировка данных в представлениях XAML"
  - "группировка данных в представлениях XAML"
  - "сортировка данных в представлениях XAML"
  - "представления, группирование данных"
  - "представления, сортировка данных"
  - "XAML, группировка данных в представлениях"
  - "XAML, сортировка данных в представлениях"
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Сортировка и группировка данных с помощью представления в XAML
В этом примере демонстрируется создание представления коллекции данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Представления предоставляют возможность группировки, сортировки, фильтрации и категоризации текущего элемента.  
  
## Пример  
 В следующем примере статический ресурс *places* определяется как коллекция объектов *Place*, в которой каждый объект *Place* состоит из названия города и штата.  Префикс *src* обозначает пространство имен, в котором определяется источник данных *Places*.  Префикс *scm* сопоставляется с пространством имен `"clr-namespace:System.ComponentModel;assembly=WindowsBase"`, а префикс *dat* — с пространством имен `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 В следующем примере создается представление коллекции данных, отсортированных по названию города и сгруппированных по штату.  
  
 [!code-xml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Представление может быть источником привязки, как в следующем примере.  
  
 [!code-xml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Для привязки к данным XML, определенным в ресурсе <xref:System.Windows.Data.XmlDataProvider>, укажите перед именем XML символ @.  
  
 [!code-xml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## См. также  
 <xref:System.Windows.Data.CollectionViewSource>   
 [Получение представления по умолчанию для коллекции данных](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)