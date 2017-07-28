---
title: "Практическое руководство. Использование шаблона &quot;основной-подробности&quot; с иерархическими данными XML | Microsoft Docs"
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
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Использование шаблона &quot;основной-подробности&quot; с иерархическими данными XML
Этот пример описывает реализацию скрипта "основной\-подробности" с данными [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
## Пример  
 Данный пример является [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-версией данных примера, рассмотренного в [Использование шаблона "главный\-подчиненный" с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  В этом примере данные поступают из файла `League.xml`.  Обратите внимание на то, как третий элемент управления <xref:System.Windows.Controls.ListBox> отслеживает изменения выделения во втором <xref:System.Windows.Controls.ListBox> путем привязки к свойству <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.  
  
 [!code-xml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## См. также  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)