---
title: "Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки | Microsoft Docs"
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
  - "диалоговые окна, создание"
  - "Grid - элемент управления, создание, диалоговое окно"
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки
В этом примере демонстрируется создание стандартного диалогового окна [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] с помощью элемента <xref:System.Windows.Controls.Grid>.  
  
## Пример  
 В следующем примере создается диалоговое окно, аналогичное диалоговому окну **Выполнить** в операционной системе [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 В примере создается элемент <xref:System.Windows.Controls.Grid> и используются классы <xref:System.Windows.Controls.ColumnDefinition> и <xref:System.Windows.Controls.RowDefinition> для определения пяти столбцов и четырех строк.  
  
 Затем в примере добавляется и размещается элемент управления <xref:System.Windows.Controls.Image> `RunIcon.png` для представления изображения, находящегося в диалоговом окне.  Изображение размещается в первом столбце первой строки сетки <xref:System.Windows.Controls.Grid> \(левый верхний угол\).  
  
 Далее в примере показано добавление элемента <xref:System.Windows.Controls.TextBlock> в первый столбец, который охватывает оставшиеся столбцы первой строки.  Во вторую строку первого столбца добавляется другой элемент <xref:System.Windows.Controls.TextBlock> для представления текстового поля **Открыть**.  Затем добавляется элемент <xref:System.Windows.Controls.TextBlock>, который представляет область ввода данных.  
  
 Наконец, в примере в последнюю строку добавляется три элемента <xref:System.Windows.Controls.Button>, которые представляют события **ОК**, **Отмена** и **Обзор**.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## См. также  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.GridUnitType>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)