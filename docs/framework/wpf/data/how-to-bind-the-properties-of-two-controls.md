---
title: "Как привязать свойства двух элементов управления | Microsoft Docs"
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
  - "связывание свойств двух элементов управления"
  - "элементы управления, связывание свойств"
  - "привязка данных, связывание свойств двух элементов управления"
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Как привязать свойства двух элементов управления
В этом примере демонстрируется, как привязать свойство одного элемента управления к другому с помощью свойства <xref:System.Windows.Data.Binding.ElementName%2A>.  
  
## Пример  
 В следующем примере показано, как привязать свойство <xref:System.Windows.Controls.Panel.Background%2A> объекта <xref:System.Windows.Controls.Canvas> к свойству <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>. <xref:System.Windows.Controls.ContentControl.Content%2A> объекта <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 При отображении этот пример выглядит следующим образом:  
  
 ![Холст с зеленым фоном](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.png "DataBindingBindingDPsSample")  
  
 **Примечание** Свойство [Цель привязки](GTMT) \(в этом примере <xref:System.Windows.Controls.Panel.Background%2A>\) должно быть [свойством зависимости](GTMT).  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## См. также  
 [Указание источника привязки](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)