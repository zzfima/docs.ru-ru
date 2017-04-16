---
title: "Практическое руководство. Привязка к результатам запроса LINQ | Microsoft Docs"
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
  - "привязка к результатам запроса LINQ [WPF]"
  - "выполнение запроса LINQ [WPF], привязка к результатам"
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Привязка к результатам запроса LINQ
Этот пример демонстрирует способ запуска запрос LINQ и последующую привязку к результатам.  
  
## Пример  
 В следующем примере создается два списка.  Первое поле списка содержит три элемента списка.  
  
 [!code-xml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 При выделении элемента в первом раскрывающемся списке вызывается следующий обработчик событий.  В этом примере `Tasks` представляет собой коллекцию объектов `Task`.  Класс `Task` имеет свойство с именем `Priority`.  Этот обработчик событий запускает запрос LINQ, возвращающий коллекцию объектов `Task`, которые имеют значение выбранного приоритета, а затем устанавливающий их как <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 Второй список привязывается к этой коллекции, так его значение <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> установлено в `{Binding}`.  В результате отображается возвращаемая коллекция \(основанная на `myTaskTemplate` <xref:System.Windows.DataTemplate>\).  
  
## См. также  
 [Обеспечение доступности данных для привязки в XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)   
 [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [Новые возможности WPF версии 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)