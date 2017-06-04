---
title: "Как проверить видимость GridSplitter | Microsoft Docs"
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
  - "GridSplitter - элемент управления, обеспечение видимости"
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Как проверить видимость GridSplitter
В этом примере показано, как проверить, что элемент управления <xref:System.Windows.Controls.GridSplitter> не скрыт другими элементами управления в объекте <xref:System.Windows.Controls.Grid>.  
  
## Пример  
 Визуализация дочерних элементов <xref:System.Windows.Controls.Panel.Children%2A> элемента управления <xref:System.Windows.Controls.Grid> осуществляется в порядке их определения в разметке или коде.  Элементы управления <xref:System.Windows.Controls.GridSplitter> можно скрыть за другими элементами управления, если не назначить их последними элементами в коллекции <xref:System.Windows.Controls.Panel.Children%2A> или задать для других элементов более высокое значение <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Чтобы предотвратить скрытие элементов управления <xref:System.Windows.Controls.GridSplitter>, выполните одно из следующих действий.  
  
-   Убедитесь, что элементы управления <xref:System.Windows.Controls.GridSplitter> являются последними в коллекции <xref:System.Windows.Controls.Panel.Children%2A>, добавленной к объекту <xref:System.Windows.Controls.Grid>.  В следующем примере показан объект <xref:System.Windows.Controls.GridSplitter> как последний элемент в коллекции <xref:System.Windows.Controls.Panel.Children%2A> объекта <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Установите значение <xref:System.Windows.Controls.Panel.ZIndexProperty> для <xref:System.Windows.Controls.GridSplitter> выше, чем элемент управления, который, в противном случае, будет его скрывать.  В следующем примере для элемента управления <xref:System.Windows.Controls.GridSplitter> устанавливается значение <xref:System.Windows.Controls.Panel.ZIndexProperty> выше, чем элемент управления <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Задайте поля для элемента управления, который иначе скрыл бы элемент управления <xref:System.Windows.Controls.GridSplitter>, таким образом, чтобы элемент управления <xref:System.Windows.Controls.GridSplitter> стал видимым.  В следующем примере устанавливаются поля для элемента управления, который иначе наложился бы на элемент управления <xref:System.Windows.Controls.GridSplitter> и скрыл его.  
  
 [!code-xml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## См. также  
 <xref:System.Windows.Controls.GridSplitter>   
 [Практические руководства](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)