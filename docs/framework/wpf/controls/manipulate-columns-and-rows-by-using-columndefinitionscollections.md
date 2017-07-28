---
title: "Практическое руководство. Управление столбцами и строками с помощью коллекций ColumnDefinitionsCollections и RowDefinitionsCollections | Microsoft Docs"
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
  - "классы, ColumnDefinitionCollection"
  - "классы, RowDefinitionCollection"
  - "ColumnDefinitionCollection - класс"
  - "элементы управления, Grid - класс"
  - "Grid - элемент управления, ColumnDefinitionCollection - класс"
  - "Grid - элемент управления, RowDefinitionCollection - класс"
  - "RowDefinitionCollection - класс"
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Управление столбцами и строками с помощью коллекций ColumnDefinitionsCollections и RowDefinitionsCollections
В этом примере показано использование методов в классах <xref:System.Windows.Controls.ColumnDefinitionCollection> и <xref:System.Windows.Controls.RowDefinitionCollection> для выполнения таких действий, как добавление, удаление или подсчет содержимого строк или столбцов.  Например, можно использовать методы <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> или свойство <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> для элементов, включенных в объекты <xref:System.Windows.Controls.ColumnDefinition> или <xref:System.Windows.Controls.RowDefinition>.  
  
## Пример  
 В следующем примере создается элемент <xref:System.Windows.Controls.Grid>, свойству <xref:System.Windows.FrameworkElement.Name%2A> которого присвоено значение `grid1`.  Элемент <xref:System.Windows.Controls.Grid> включает в себя объект <xref:System.Windows.Controls.StackPanel>, который содержит элементы <xref:System.Windows.Controls.Button>, управляющие различными методами коллекции.  При нажатии элемента <xref:System.Windows.Controls.Button> активируется вызов метода в файле кода программной части.  
  
 [!code-xml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 В этом примере определяется ряд пользовательских методов, каждый из которых соответствует событию <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в файле [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Предусмотрено несколько способов изменения числа столбцов и строк в объекте <xref:System.Windows.Controls.Grid>, включая добавление или удаление строк и столбцов, а также подсчет общего числа строк и столбцов.  Чтобы предотвратить возникновение исключений <xref:System.ArgumentOutOfRangeException> и <xref:System.ArgumentException>, рекомендуется использовать функцию проверки ошибок, предоставляемую методом <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A>.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.ColumnDefinitionCollection>   
 <xref:System.Windows.Controls.RowDefinitionCollection>