---
title: Практическое руководство. Обеспечение доступности данных для привязки в XAML
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 09a6fca48c06efca6f06b9e0617de9095197bd17
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070803"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Практическое руководство. Обеспечение доступности данных для привязки в XAML
В этом разделе рассматриваются различные способы, которые можно сделать данные доступными для привязки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], в зависимости от потребностей приложения.  
  
## <a name="example"></a>Пример  
 Если у вас есть [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объекта, вы бы хотели привязки из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], один из способов, вы можете сделать объект доступным для привязки является определение его как ресурс и присвойте ему `x:Key`. В следующем примере имеется `Person` объект с строковое свойство с именем `PersonName`. `Person` Объекта (в строке, выделено, содержащий `<src>` элемент) определен в пространстве имен `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Затем можно привязать <xref:System.Windows.Controls.TextBlock> управления к объекту в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], как выделенная строка содержит `<TextBlock>` показан элемент. 
  
 Кроме того, можно использовать <xref:System.Windows.Data.ObjectDataProvider> класса, как показано в следующем примере:  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Привязка определяется так же, как выделенные строки, содержащей `<TextBlock>` показан элемент.  
  
 В данном конкретном примере результат одинаков: у вас есть <xref:System.Windows.Controls.TextBlock> с текстовым содержимым `Joe`. Тем не менее <xref:System.Windows.Data.ObjectDataProvider> класс предоставляет функциональные возможности, такие как возможность привязки к результату метода. Вы можете использовать <xref:System.Windows.Data.ObjectDataProvider> , если вы нуждаетесь в функциях, он предоставляет.  
  
 Тем не менее, если выполнить привязку к объекту, который уже был создан, необходимо задать `DataContext` в коде, как показано в следующем примере.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Чтобы получить доступ к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные с помощью привязки <xref:System.Windows.Data.XmlDataProvider> , представлена в разделе [привязка к данным XML с помощью XMLDataProvider и запросов XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Чтобы получить доступ к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные с помощью привязки <xref:System.Windows.Data.ObjectDataProvider> , представлена в разделе [привязка к XDocument, XElement или LINQ для результатов запросов XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Сведения о многом, можно указать данные, при привязке к, см. в разделе [Указание источника привязки](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md). Сведения о типы данных можно привязать к или как реализовать собственные [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объекты для привязки, см. в разделе [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
