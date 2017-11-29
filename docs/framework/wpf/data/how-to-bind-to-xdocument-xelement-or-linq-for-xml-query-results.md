---
title: "Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b39c45a7c85155a0fb46e8e176da5979e52e6e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML
В этом примере показано, как выполнить привязку данных XML для <xref:System.Windows.Controls.ItemsControl> с помощью <xref:System.Xml.Linq.XDocument>.  
  
## <a name="example"></a>Пример  
 Следующий код XAML определяет <xref:System.Windows.Controls.ItemsControl> и включает шаблон данных для данных типа `Planet` в `http://planetsNS` пространства имен XML. Тип данных XML, заполняющий пространство имен, должен включать пространство имен, заключенное в фигурные скобки, или (при отображении вместе с расширением разметки XAML) предшествовать пространству имен с escape-последовательностью в фигурных скобках. Этот код выполняет привязку к динамическим свойствам, которые соответствуют <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> методы <xref:System.Xml.Linq.XElement> класса. Динамические свойства включают XAML для привязки к динамическим свойствам, предоставляющим доступ к именам методов. Дополнительные сведения см. в разделе [Динамические свойства LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties). Обратите внимание на то, что объявление пространства имен по умолчанию для XML не применяется к именам атрибутов.  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 Следующий код вызывает C# <xref:System.Xml.Linq.XDocument.Load%2A> и задает контекст данных панели стека для всех подэлементов элемента с именем `SolarSystemPlanets` в `http://planetsNS` пространства имен XML.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 XML-данные можно сохранить в качестве ресурсов XAML с помощью <xref:System.Windows.Data.ObjectDataProvider>. Полный пример см. в разделе [Исходный код L2DBForm.xaml](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e). В следующем примере показано, каким образом код может задавать контекст данных для ресурса объекта.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Динамические свойства, которые сопоставляются с <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> обеспечивают гибкость в XAML. Код также можно привязать к результатам запроса LINQ для XML. В этом примере он привязывается к результатам запроса, направленного значением элемента.  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Общие сведения о привязке данных WPF с помощью LINQ to XML](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [Привязка данных WPF с использованием примера LINQ to XML](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)  
 [Динамические свойства LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties)
