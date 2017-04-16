---
title: "Практическое руководство. Создание значений на основе списка связанных элементов | Microsoft Docs"
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
  - "привязка данных, MultiBinding"
  - "MultiBinding"
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Создание значений на основе списка связанных элементов
Возможности класса <xref:System.Windows.Data.MultiBinding> позволяют связать свойство [объекта привязки](GTMT) со списком свойств источника и затем применить логику для получения значения с заданными входными данными.  В этом примере демонстрируется использование класса <xref:System.Windows.Data.MultiBinding>.  
  
## Пример  
 В следующем примере объект `NameListData` ссылается на коллекцию объектов `PersonName`, которые содержат свойства `firstName` и `lastName`.  В следующем примере создается экземпляр класса <xref:System.Windows.Controls.TextBlock>, который используется для отображения имени и фамилии человека \(сначала указывается фамилия\).  
  
 [!code-xml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Чтобы понять, как получается формат «фамилия\-имя», просмотрите реализацию `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 Интерфейс `NameConverter` реализует интерфейс <xref:System.Windows.Data.IMultiValueConverter>.  `NameConverter` принимает значения от отдельных привязок и сохраняет их в массиве объектов значений.  Порядок, в котором отображаются элементы <xref:System.Windows.Data.Binding> в элементе <xref:System.Windows.Data.MultiBinding>, соответствует порядку хранения этих значений в массиве.  На значение атрибута <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> ссылается аргумент параметра метода <xref:System.Windows.Data.MultiBinding.Converter%2A>, который переключается на параметр для определения способа форматирования имени.  
  
## См. также  
 [Преобразование привязанных данных](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)