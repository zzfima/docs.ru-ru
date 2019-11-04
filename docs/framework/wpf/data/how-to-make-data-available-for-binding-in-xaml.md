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
ms.openlocfilehash: 2bfd9809a6ad487a7e706366dc6bce8fe951c940
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459765"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Практическое руководство. Обеспечение доступности данных для привязки в XAML
В этом разделе обсуждаются различные способы обеспечения доступности данных для привязки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]в зависимости от потребностей приложения.  
  
## <a name="example"></a>Пример  
 Если у вас есть объект среды CLR, к которому вы хотите выполнить привязку [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно сделать объект доступным для привязки, чтобы определить его как ресурс и присвоить ему `x:Key`. В следующем примере имеется объект `Person` со строковым свойством с именем `PersonName`. Объект `Person` (в строке, выделенной цветом, который содержит элемент `<src>`), определяется в пространстве имен с именем `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Затем можно привязать элемент управления <xref:System.Windows.Controls.TextBlock> к объекту в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], так как отображается выделенная линия, содержащая элемент `<TextBlock>`. 
  
 Кроме того, можно использовать класс <xref:System.Windows.Data.ObjectDataProvider>, как показано в следующем примере:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Привязка определяется таким же образом, как и выделенная линия, содержащая элемент `<TextBlock>`.  
  
 В этом конкретном примере результат будет таким же: у вас есть <xref:System.Windows.Controls.TextBlock> с текстовым содержимым `Joe`. Однако класс <xref:System.Windows.Data.ObjectDataProvider> предоставляет такие функции, как возможность привязки к результату метода. Можно выбрать использование класса <xref:System.Windows.Data.ObjectDataProvider>, если требуются предоставляемые им функции.  
  
 Однако при привязке к уже созданному объекту необходимо задать `DataContext` в коде, как показано в следующем примере.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Сведения о том, как получить доступ к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] для привязки с помощью класса <xref:System.Windows.Data.XmlDataProvider>, см. в разделе [Bind to XML Data using a XmlDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Сведения о том, как получить доступ к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] для привязки с помощью класса <xref:System.Windows.Data.ObjectDataProvider>, см. [в разделе Bind to XDocument, XElement или LINQ for XML Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Дополнительные сведения о различных способах указания данных, к которым выполняется привязка, см. в разделе [Указание источника привязки](how-to-specify-the-binding-source.md). Сведения о типах данных, к которым можно выполнить привязку, или о том, как реализовать собственные объекты среды CLR для привязки, см. в разделе [Общие сведения об источниках привязки](binding-sources-overview.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
