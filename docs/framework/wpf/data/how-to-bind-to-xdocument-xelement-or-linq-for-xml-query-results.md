---
title: "Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML | Microsoft Docs"
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
  - "привязка данных [WPF], привязка к XDocument"
  - "привязка данных [WPF], привязка к XElement"
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML
В этом примере показано, как выполнить привязку данных XML к <xref:System.Windows.Controls.ItemsControl> с помощью <xref:System.Xml.Linq.XDocument>.  
  
## Пример  
 Следующий код XAML определяет <xref:System.Windows.Controls.ItemsControl> и включает шаблон данных для данных типа `Planet` в пространство имен XML `http://planetsNS`.  Тип данных XML, заполняющих пространство имен, должен включать пространство имен в фигурных скобках, и если оно появляется в том месте, где может отображаться расширение разметки XAML, перед ним должно быть указано пространство имен с escape\-последовательностью фигурной скобки.  Этот код выполняет привязку к динамическим свойствам соответственно методам <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> класса <xref:System.Xml.Linq.XElement>.  Динамические свойства включают XAML для привязки к динамическим свойствам, общим для имен методов.  Дополнительные сведения см. в разделе [Динамические свойства LINQ to XML](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md).  Обратите внимание, как объявление пространства имен по умолчанию для XML не применяется к именам атрибутов.  
  
 [!code-xml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 Следующий код C\# вызывает метод <xref:System.Xml.Linq.XDocument.Load%2A> и задает контекст данных панели\-стопки для всех подэлементов элемента с именем `SolarSystemPlanets` в пространстве имен XML `http://planetsNS`.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 Данные XML можно сохранить как ресурс XAML с помощью <xref:System.Windows.Data.ObjectDataProvider>.  Полный пример см. в разделе [Исходный код L2DBForm.xaml](../Topic/L2DBForm.xaml%20Source%20Code.md).  В следующем примере показано, как код может задать контекст данных ресурсу объекта.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Динамические свойства, сопоставляемые методу <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A>, обеспечивают гибкость внутри кода XAML.  Код может также выполнить привязку к результатам запроса LINQ для XML.  В этом примере выполняется привязка к результатам запроса, сделанного значением элемента.  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## См. также  
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Общие сведения о связывании с данными в WPF с помощью LINQ to XML](../Topic/WPF%20Data%20Binding%20with%20LINQ%20to%20XML%20Overview.md)   
 [Пример связывания с данными в WPF с помощью LINQ to XML](../Topic/WPF%20Data%20Binding%20Using%20LINQ%20to%20XML%20Example.md)   
 [Динамические свойства LINQ to XML](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md)