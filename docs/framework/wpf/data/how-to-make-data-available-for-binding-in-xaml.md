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
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174190"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="05af9-102">Практическое руководство. Обеспечение доступности данных для привязки в XAML</span><span class="sxs-lookup"><span data-stu-id="05af9-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="05af9-103">Эта тема обсуждает различные способы, которыми можно сделать данные доступными для связывания в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]зависимости от потребностей приложения.</span><span class="sxs-lookup"><span data-stu-id="05af9-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05af9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="05af9-104">Example</span></span>  
 <span data-ttu-id="05af9-105">Если у вас есть общий язык времени выполнения (CLR) объект, который вы хотели бы привязать к от [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], `x:Key`один из способов вы можете сделать объект доступным для связывания, чтобы определить его как ресурс и дать ему .</span><span class="sxs-lookup"><span data-stu-id="05af9-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="05af9-106">В следующем примере у `Person` вас есть объект `PersonName`с именем свойства строки.</span><span class="sxs-lookup"><span data-stu-id="05af9-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="05af9-107">Объект `Person` (в строке, показанной, `<src>` которая содержит элемент) определяется в подзванном `SDKSample`пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="05af9-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="05af9-108">Затем можно связать <xref:System.Windows.Controls.TextBlock> элемент управления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]с объектом в, как `<TextBlock>` показано выделенной строке, содержащей элемент.</span><span class="sxs-lookup"><span data-stu-id="05af9-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="05af9-109">Кроме того, вы <xref:System.Windows.Data.ObjectDataProvider> можете использовать класс, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="05af9-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="05af9-110">Связывание определяется таким же образом, как `<TextBlock>` показано на выделенной строке, содержащей элемент.</span><span class="sxs-lookup"><span data-stu-id="05af9-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="05af9-111">В данном конкретном примере результат тот <xref:System.Windows.Controls.TextBlock> же: у `Joe`вас есть с текстовым контентом.</span><span class="sxs-lookup"><span data-stu-id="05af9-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="05af9-112">Тем не <xref:System.Windows.Data.ObjectDataProvider> менее, класс предоставляет такие функциональные возможности, как возможность привязываться к результату метода.</span><span class="sxs-lookup"><span data-stu-id="05af9-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="05af9-113">Вы можете использовать <xref:System.Windows.Data.ObjectDataProvider> класс, если вам нужна функция, которая она предоставляет.</span><span class="sxs-lookup"><span data-stu-id="05af9-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="05af9-114">Однако, если вы привязываетесь к объекту, `DataContext` который уже создан, необходимо установить код, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="05af9-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="05af9-115">Чтобы получить доступ к данным <xref:System.Windows.Data.XmlDataProvider> XML для связывания с помощью класса, см. [Привязка к данным XML С помощью XMLDataProvider и XPath-запросов.](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)</span><span class="sxs-lookup"><span data-stu-id="05af9-115">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="05af9-116">Для доступа к данным XML для связывания с <xref:System.Windows.Data.ObjectDataProvider> помощью класса см. [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="05af9-116">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="05af9-117">Для получения информации о многих способах указания связываемых данных [см.](how-to-specify-the-binding-source.md)</span><span class="sxs-lookup"><span data-stu-id="05af9-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="05af9-118">Для получения информации о том, какие типы данных можно связывать или как реализовать объекты общего времени выполнения языка (CLR) для связывания, [см.](binding-sources-overview.md)</span><span class="sxs-lookup"><span data-stu-id="05af9-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05af9-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="05af9-119">See also</span></span>

- [<span data-ttu-id="05af9-120">Обзор связывания данных</span><span class="sxs-lookup"><span data-stu-id="05af9-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="05af9-121">Как-к темам</span><span class="sxs-lookup"><span data-stu-id="05af9-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
