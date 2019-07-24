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
ms.openlocfilehash: 3487a160cc49ab6b779a20157668915c2da33900
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401493"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Практическое руководство. Обеспечение доступности данных для привязки в XAML
В этом разделе обсуждаются различные способы обеспечения доступности данных для привязки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]в зависимости от потребностей приложения.  
  
## <a name="example"></a>Пример  
 Если у вас есть объект среды CLR [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], к которому вы хотите выполнить привязку, можно сделать объект доступным для привязки, чтобы определить его как ресурс и присвоить `x:Key`ему значение. В следующем примере имеется `Person` объект со строковым свойством с именем. `PersonName` Объект (в строке, выделенной цветом, который `<src>` содержит элемент) определяется в пространстве имен с именем `SDKSample`. `Person`  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Затем можно привязать <xref:System.Windows.Controls.TextBlock> элемент управления к объекту в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], так как в `<TextBlock>` выделенной строке, содержащей элемент, отображается. 
  
 Кроме того, можно использовать <xref:System.Windows.Data.ObjectDataProvider> класс, как показано в следующем примере:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Привязка определяется таким же образом, как и выделенная строка, содержащая `<TextBlock>` элемент.  
  
 В этом конкретном примере результат будет таким же: у вас есть <xref:System.Windows.Controls.TextBlock> с текстовым содержимым. `Joe` <xref:System.Windows.Data.ObjectDataProvider> Однако класс предоставляет такие функциональные возможности, как возможность привязки к результату метода. Можно выбрать использование <xref:System.Windows.Data.ObjectDataProvider> класса, если требуется предоставляемая им функциональность.  
  
 Однако при привязке к объекту, который уже был создан, необходимо задать `DataContext` в коде, как показано в следующем примере.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Сведения о [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] доступе к данным для <xref:System.Windows.Data.XmlDataProvider> привязки с помощью класса см. в разделе [Bind to XML Data using a XmlDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Сведения о [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] доступе к данным для <xref:System.Windows.Data.ObjectDataProvider> привязки с помощью класса см. в разделе [Bind to XDocument, XElement или LINQ for XML Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Дополнительные сведения о различных способах указания данных, к которым выполняется привязка, см. в разделе [Указание источника привязки](how-to-specify-the-binding-source.md). Сведения о типах данных, к которым можно выполнить привязку, или о том, как реализовать собственные объекты среды CLR для привязки, см. в разделе [Общие сведения об источниках привязки](binding-sources-overview.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
