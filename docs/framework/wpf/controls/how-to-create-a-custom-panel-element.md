---
title: "Практическое руководство. Создание пользовательского элемента Panel | Microsoft Docs"
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
  - "пользовательские элементы Panel"
  - "Panel - элемент управления"
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание пользовательского элемента Panel
## Пример  
 В этом примере демонстрируется переопределение поведения макета по умолчанию для элемента <xref:System.Windows.Controls.Panel> и создание пользовательских элементов макета, производных от <xref:System.Windows.Controls.Panel>.  
  
 В этом примере определяется простой пользовательский элемент <xref:System.Windows.Controls.Panel> с именем `PlotPanel`, который размещает дочерние элементы в соответствии с двумя заданными в коде координатами x и y.  В этом примере `x` и `y` равны `50`; таким образом, все дочерние элементы расположены на одинаковом расстоянии от осей x и y.  
  
 Чтобы реализовать поведение пользовательской <xref:System.Windows.Controls.Panel>, в примере используются методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  Каждый метод возвращает данные <xref:System.Windows.Size>, необходимые для размещения и отображения дочерних элементов.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## См. также  
 <xref:System.Windows.Controls.Panel>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Create a Custom Content\-Wrapping Panel Sample](http://go.microsoft.com/fwlink/?LinkID=159979)