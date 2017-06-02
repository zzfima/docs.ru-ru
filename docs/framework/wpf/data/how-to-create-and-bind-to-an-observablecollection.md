---
title: "Практическое руководство. Создание и привязка коллекции &quot;ObservableCollection&quot; | Microsoft Docs"
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
  - "классы, ObservableCollection"
  - "привязка данных, ObservableCollection - класс"
  - "уведомления"
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Создание и привязка коллекции &quot;ObservableCollection&quot;
В этом примере демонстрируется создание и привязка коллекции, производной от класса <xref:System.Collections.ObjectModel.ObservableCollection%601>, который является классом коллекции, предоставляющим уведомления при добавлении или удалении элементов.  
  
## Пример  
 В следующем примере показана реализация коллекции `NameList`:  
  
 [!code-csharp[MultiBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[MultiBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameList.vb#1)]  
  
 Можно сделать коллекцию доступной для привязки тем же способом, который используется для привязки других объектов [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], как описано в разделе [Обеспечение доступности данных для привязки в XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).  Например, можно создать экземпляр коллекции в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и указать коллекцию в качестве ресурса, как показано ниже:  
  
 [!code-xml[MultiBinding#OCHowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#ochowto)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
  
 Затем можно выполнить привязку к коллекции:  
  
 [!code-xml[MultiBinding#MultiBindingListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindinglistbox)]  
  
 Определение `NameItemTemplate` здесь не показано.  
  
> [!NOTE]
>  Объекты в коллекции должны удовлетворять требованиям, описанным в разделе [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  В частности, при использовании свойства <xref:System.Windows.Data.BindingMode> или <xref:System.Windows.Data.BindingMode> \(например, в случае необходимости обновлять [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] при динамическом изменении свойств источника\) необходимо реализовать подходящий механизм уведомления об изменении свойства, такой как интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Дополнительные сведения см. в подразделе «Привязка к коллекции» раздела [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## См. также  
 [Сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Сортировка и группировка данных с помощью представления в XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)