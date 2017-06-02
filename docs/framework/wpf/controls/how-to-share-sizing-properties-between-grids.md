---
title: "Практическое руководство. Совместное использование свойств размера между сетками | Microsoft Docs"
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
  - "Grid - элемент управления, совместное использование данных столбцов"
  - "Grid - элемент управления, совместное использование данных строк"
  - "изменение размера данных в элементах управления Grid"
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Совместное использование свойств размера между сетками
В этом примере показано применение общего доступа к данным размера столбцов и строк для элементов <xref:System.Windows.Controls.Grid>, чтобы сохранить согласованное изменение размеров.  
  
## Пример  
 В следующем примере два элемента <xref:System.Windows.Controls.Grid> представлены как дочерние элементы родительского элемента <xref:System.Windows.Controls.DockPanel>.  [Вложенное свойство](GTMT) <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> элемента управления <xref:System.Windows.Controls.Grid> определяется в родительском элементе <xref:System.Windows.Controls.DockPanel>.  
  
 В примере значение свойства управляется с помощью двух элементов <xref:System.Windows.Controls.Button>; каждый элемент представляет одно из значений свойств логического типа.  Если значение свойства <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> равно `true`, то каждый столбец или строка <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> используют общие сведения о размере, независимо от содержимого строки или столбца.  
  
 [!code-xml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 В следующем примере кода программной части обрабатываются методы, вызываемые событием нажатия кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  Далее результаты вызовов этих методов записывается в элементы <xref:System.Windows.Controls.TextBlock>, которые используют связанные методы получения для вывода новых значений свойств в виде строк.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## См. также  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)