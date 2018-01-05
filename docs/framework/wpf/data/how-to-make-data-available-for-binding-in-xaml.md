---
title: "Практическое руководство. Обеспечение доступности данных для привязки в XAML"
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
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c342f0d635a9220a88a2af79c76e2c1580dee2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="9ee29-102">Практическое руководство. Обеспечение доступности данных для привязки в XAML</span><span class="sxs-lookup"><span data-stu-id="9ee29-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="9ee29-103">В этом разделе обсуждаются различные способы, вы можете сделать данные доступными для привязки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], в зависимости от требований приложения.</span><span class="sxs-lookup"><span data-stu-id="9ee29-103">This topic discusses the different ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ee29-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9ee29-104">Example</span></span>  
 <span data-ttu-id="9ee29-105">Если у вас есть [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объекта вы бы хотели привязки из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], один из способов сделать объект доступен для привязки является определение его в качестве ресурса и присвоить ему `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="9ee29-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="9ee29-106">В следующем примере у вас есть `Person` объект с строковое свойство с именем `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="9ee29-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="9ee29-107">`Person` Объект определен в пространстве имен `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="9ee29-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="9ee29-108">Затем можно привязать к объекту в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9ee29-108">You can then bind to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as shown in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="9ee29-109">Кроме того, можно использовать <xref:System.Windows.Data.ObjectDataProvider> класса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9ee29-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 <span data-ttu-id="9ee29-110">Привязка определяется так же, как:</span><span class="sxs-lookup"><span data-stu-id="9ee29-110">You define the binding the same way:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="9ee29-111">В этом примере, результат будет такой же: у вас есть <xref:System.Windows.Controls.TextBlock> с текстовым содержимым `Joe`.</span><span class="sxs-lookup"><span data-stu-id="9ee29-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="9ee29-112">Тем не менее <xref:System.Windows.Data.ObjectDataProvider> класс предоставляет функциональные возможности, такие как возможность привязки к результату метода.</span><span class="sxs-lookup"><span data-stu-id="9ee29-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="9ee29-113">Вы можете использовать <xref:System.Windows.Data.ObjectDataProvider> класса, если требуется, чтобы он предоставляет функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="9ee29-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="9ee29-114">Однако при привязке для объекта, который уже был создан, необходимо задать `DataContext` в коде, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9ee29-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="9ee29-115">Чтобы получить доступ к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные с помощью привязки <xref:System.Windows.Data.XmlDataProvider> см. в описании [связывания XML-данных с помощью XMLDataProvider и запросы XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9ee29-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="9ee29-116">Чтобы получить доступ к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные с помощью привязки <xref:System.Windows.Data.ObjectDataProvider> см. в разделе [Bind XDocument XElement и LINQ для результатов запроса XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="9ee29-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="9ee29-117">Сведения о различных способах можно указать данные, привязка осуществляется к см. в разделе [указать источник привязки](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="9ee29-117">For information about the different ways you can specify the data you are binding to, see [Specify the Binding Source](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="9ee29-118">Сведения о типы данных можно привязать к или как реализовать собственные [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объектов для привязки, в разделе [Общие сведения о привязке источников](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ee29-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee29-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9ee29-119">See Also</span></span>  
 [<span data-ttu-id="9ee29-120">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="9ee29-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="9ee29-121">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="9ee29-121">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
