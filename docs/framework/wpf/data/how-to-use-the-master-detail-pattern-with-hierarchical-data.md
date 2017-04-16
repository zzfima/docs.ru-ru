---
title: "Практическое руководство. Использование шаблона &quot;основной-подчиненный&quot; с иерархическими данными | Microsoft Docs"
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
  - "привязка данных, Master-Detail - парадигма данных"
  - "Master-Detail - парадигма данных"
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Использование шаблона &quot;основной-подчиненный&quot; с иерархическими данными
В этом примере описывается, как реализовать скрипт с отношением «основной\-подчиненный».  
  
## Пример  
 В этом примере `LeagueList` представляет собой коллекцию `Leagues`.  Каждый `League` имеет `Name` и коллекцию `Divisions`, а каждый `Division` содержит имя и коллекцию `Teams`.  Каждый `Team` содержит имя команды.  
  
 [!code-xml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Ниже приведен снимок экрана этого примера.  `Divisions` <xref:System.Windows.Controls.ListBox> автоматически отслеживает выделение в`Leagues` <xref:System.Windows.Controls.ListBox> и отображает соответствующие данные.  `Teams` <xref:System.Windows.Controls.ListBox> отслеживает выбор в двух других элементах управления <xref:System.Windows.Controls.ListBox>.  
  
 ![Подробный пример](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 В данном примере следует обратить внимание на два обстоятельства:  
  
1.  Три элемента управления <xref:System.Windows.Controls.ListBox> привязываются к одному источнику.  Необходимо установить свойство <xref:System.Windows.Data.Binding.Path%2A> привязки для определения уровня данных, которые нужно отобразить в <xref:System.Windows.Controls.ListBox>.  
  
2.  Необходимо задать для свойства <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> значение `true` для элемента управления <xref:System.Windows.Controls.ListBox>, из которого осуществляется отслеживание выбора.  Установка этого свойства гарантирует, что выбранный элемент всегда задается как свойство <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.  Альтернативно, если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, то он автоматически синхронизирует выбор и денежные единицы.  
  
 При использовании данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] применяется несколько иной метод.  Пример см. в разделе [Использование шаблона "главный\-подчиненный" с иерархическими XML\-данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## См. также  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)