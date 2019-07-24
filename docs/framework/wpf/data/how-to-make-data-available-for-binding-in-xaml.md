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
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="b3038-102">Практическое руководство. Обеспечение доступности данных для привязки в XAML</span><span class="sxs-lookup"><span data-stu-id="b3038-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="b3038-103">В этом разделе обсуждаются различные способы обеспечения доступности данных для привязки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]в зависимости от потребностей приложения.</span><span class="sxs-lookup"><span data-stu-id="b3038-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3038-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b3038-104">Example</span></span>  
 <span data-ttu-id="b3038-105">Если у вас есть объект среды CLR [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], к которому вы хотите выполнить привязку, можно сделать объект доступным для привязки, чтобы определить его как ресурс и присвоить `x:Key`ему значение.</span><span class="sxs-lookup"><span data-stu-id="b3038-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="b3038-106">В следующем примере имеется `Person` объект со строковым свойством с именем. `PersonName`</span><span class="sxs-lookup"><span data-stu-id="b3038-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="b3038-107">Объект (в строке, выделенной цветом, который `<src>` содержит элемент) определяется в пространстве имен с именем `SDKSample`. `Person`</span><span class="sxs-lookup"><span data-stu-id="b3038-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="b3038-108">Затем можно привязать <xref:System.Windows.Controls.TextBlock> элемент управления к объекту в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], так как в `<TextBlock>` выделенной строке, содержащей элемент, отображается.</span><span class="sxs-lookup"><span data-stu-id="b3038-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="b3038-109">Кроме того, можно использовать <xref:System.Windows.Data.ObjectDataProvider> класс, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b3038-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="b3038-110">Привязка определяется таким же образом, как и выделенная строка, содержащая `<TextBlock>` элемент.</span><span class="sxs-lookup"><span data-stu-id="b3038-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="b3038-111">В этом конкретном примере результат будет таким же: у вас есть <xref:System.Windows.Controls.TextBlock> с текстовым содержимым. `Joe`</span><span class="sxs-lookup"><span data-stu-id="b3038-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="b3038-112"><xref:System.Windows.Data.ObjectDataProvider> Однако класс предоставляет такие функциональные возможности, как возможность привязки к результату метода.</span><span class="sxs-lookup"><span data-stu-id="b3038-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="b3038-113">Можно выбрать использование <xref:System.Windows.Data.ObjectDataProvider> класса, если требуется предоставляемая им функциональность.</span><span class="sxs-lookup"><span data-stu-id="b3038-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="b3038-114">Однако при привязке к объекту, который уже был создан, необходимо задать `DataContext` в коде, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b3038-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="b3038-115">Сведения о [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] доступе к данным для <xref:System.Windows.Data.XmlDataProvider> привязки с помощью класса см. в разделе [Bind to XML Data using a XmlDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b3038-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="b3038-116">Сведения о [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] доступе к данным для <xref:System.Windows.Data.ObjectDataProvider> привязки с помощью класса см. в разделе [Bind to XDocument, XElement или LINQ for XML Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="b3038-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="b3038-117">Дополнительные сведения о различных способах указания данных, к которым выполняется привязка, см. в разделе [Указание источника привязки](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="b3038-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="b3038-118">Сведения о типах данных, к которым можно выполнить привязку, или о том, как реализовать собственные объекты среды CLR для привязки, см. в разделе [Общие сведения об источниках привязки](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b3038-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3038-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b3038-119">See also</span></span>

- [<span data-ttu-id="b3038-120">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="b3038-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="b3038-121">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="b3038-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
