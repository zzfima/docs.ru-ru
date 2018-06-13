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
ms.openlocfilehash: dd66fb2f96f8c42fea36afaeda0aaf35a2adbace
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557333"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Практическое руководство. Обеспечение доступности данных для привязки в XAML
В этом разделе обсуждаются различные способы, вы можете сделать данные доступными для привязки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], в зависимости от требований приложения.  
  
## <a name="example"></a>Пример  
 Если у вас есть [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объекта вы бы хотели привязки из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], один из способов сделать объект доступен для привязки является определение его в качестве ресурса и присвоить ему `x:Key`. В следующем примере у вас есть `Person` объект с строковое свойство с именем `PersonName`. `Person` Объекта, который отображается по выделенная строка, содержащий `<src>` элемент, определен в пространстве имен `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 После этого можно связать <xref:System.Windows.Controls.TextBlock> управления к объекту в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], как выделенная строка содержит `<TextBlock>` показывает элемент. 
  
 Кроме того, можно использовать <xref:System.Windows.Data.ObjectDataProvider> класса, как показано в следующем примере:  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Привязка определяется так же, как выделенная строка, содержащий `<TextBlock>` показывает элемент.  
  
 В этом примере, результат будет такой же: у вас есть <xref:System.Windows.Controls.TextBlock> с текстовым содержимым `Joe`. Тем не менее <xref:System.Windows.Data.ObjectDataProvider> класс предоставляет функциональные возможности, такие как возможность привязки к результату метода. Вы можете использовать <xref:System.Windows.Data.ObjectDataProvider> класса, если требуется, чтобы он предоставляет функциональные возможности.  
  
 Однако при привязке для объекта, который уже был создан, необходимо задать `DataContext` в коде, как показано в следующем примере.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Чтобы получить доступ к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные с помощью привязки <xref:System.Windows.Data.XmlDataProvider> см. в описании [связывания XML-данных с помощью XMLDataProvider и запросы XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Чтобы получить доступ к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные с помощью привязки <xref:System.Windows.Data.ObjectDataProvider> см. в разделе [Bind XDocument XElement и LINQ для результатов запроса XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Сведения о различных способах можно указать данные, привязка осуществляется к см. в разделе [указать источник привязки](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md). Сведения о типы данных можно привязать к или как реализовать собственные [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объектов для привязки, в разделе [Общие сведения о привязке источников](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
