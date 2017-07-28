---
title: "Как реализовать CompositeCollection | Microsoft Docs"
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
  - "классы, CompositeCollection"
  - "привязка данных, класс CompositeCollection"
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Как реализовать CompositeCollection
## Пример  
 В следующем примере показано, как отобразить несколько коллекций и элементов в одном списке с помощью класса <xref:System.Windows.Data.CompositeCollection>.  В этом примере `GreekGods` является объектом <xref:System.Collections.ObjectModel.ObservableCollection%601> пользовательских объектов `GreekGod`.  Шаблоны данных определены таким образом, что объекты `GreekGod` и `GreekHero` отображаются желтым и голубым фоновым цветом соответственно.  
  
 [!code-xml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## См. также  
 <xref:System.Windows.Data.CollectionContainer>   
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>   
 <xref:System.Windows.Data.XmlDataProvider>   
 <xref:System.Windows.DataTemplate>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)