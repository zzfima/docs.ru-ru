---
title: "Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента | Microsoft Docs"
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
  - "привязка данных, привязка к коллекциям"
  - "привязка данных, создание представлений коллекций данных"
  - "привязка данных, выбор данных для представлений"
  - "коллекции данных, выбор данных для представлений"
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента
Рассмотрим простой скрипт с отношением «главный\-подчиненный», в котором имеется объект <xref:System.Windows.Controls.ItemsControl> с привязкой данных, например, элемент управления <xref:System.Windows.Controls.ListBox>.  В зависимости от выбора пользователя можно отобразить дополнительные сведения о выбранном элементе.  В данном примере показано, как реализовать этот скрипт.  
  
## Пример  
 В данном примере `People` является объектом <xref:System.Collections.ObjectModel.ObservableCollection%601> классов `Person`.  Данный класс `Person` содержит три свойства: `FirstName`, `LastName` и `HomeTown`. Все свойства являются типом `string`.  
  
 [!code-xml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Объект <xref:System.Windows.Controls.ContentControl> использует объект <xref:System.Windows.DataTemplate>, определяющий способ представления сведений о `Person`:  
  
 [!code-xml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Ниже приведен снимок экрана с результатом выполнения примера.  Объект <xref:System.Windows.Controls.ContentControl> отображает другие свойства выбранного лица.  
  
 ![Привязка к коллекции](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding\_CollectionBindingSample")  
  
 В данном примере следует обратить внимание на два обстоятельства:  
  
1.  <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ContentControl> привязаны к одному источнику.  Свойства <xref:System.Windows.Data.Binding.Path%2A> обеих привязок не заданы, так как оба элемента управления привязаны к объекту коллекции.  
  
2.  Для правильной работы необходимо задать для свойства <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> значение `true`.  Установка этого свойства гарантирует, что выбранный элемент всегда задается как свойство <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.  Альтернативно, если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, то он автоматически синхронизирует выбор и денежные единицы.  
  
 Обратите внимание, что класс `Person` переопределяет метод `ToString` следующим образом.  По умолчанию <xref:System.Windows.Controls.ListBox> вызывает метод `ToString` и отображает строковое представление каждого объекта в присоединенной коллекции.  Поэтому каждый объект `Person` отображается как имя в <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## См. также  
 [Использование шаблона "главный\-подчиненный" с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)   
 [Использование шаблона "главный\-подчиненный" с иерархическими XML\-данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)