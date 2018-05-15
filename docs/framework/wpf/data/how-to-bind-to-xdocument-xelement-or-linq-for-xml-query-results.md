---
title: Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 7e4f9cc2f5e6815a35b4911f5b4a480161d66ef3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="45c8f-102">Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML</span><span class="sxs-lookup"><span data-stu-id="45c8f-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>
<span data-ttu-id="45c8f-103">В этом примере показано, как выполнить привязку данных XML для <xref:System.Windows.Controls.ItemsControl> с помощью <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="45c8f-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45c8f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="45c8f-104">Example</span></span>  
 <span data-ttu-id="45c8f-105">Следующий код XAML определяет <xref:System.Windows.Controls.ItemsControl> и включает шаблон данных для данных типа `Planet` в `http://planetsNS` пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="45c8f-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="45c8f-106">Тип данных XML, заполняющий пространство имен, должен включать пространство имен, заключенное в фигурные скобки, или (при отображении вместе с расширением разметки XAML) предшествовать пространству имен с escape-последовательностью в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="45c8f-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="45c8f-107">Этот код выполняет привязку к динамическим свойствам, которые соответствуют <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> методы <xref:System.Xml.Linq.XElement> класса.</span><span class="sxs-lookup"><span data-stu-id="45c8f-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="45c8f-108">Динамические свойства включают XAML для привязки к динамическим свойствам, предоставляющим доступ к именам методов.</span><span class="sxs-lookup"><span data-stu-id="45c8f-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="45c8f-109">Дополнительные сведения см. в разделе [Динамические свойства LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties).</span><span class="sxs-lookup"><span data-stu-id="45c8f-109">To learn more, see [LINQ to XML Dynamic Properties](/visualstudio/designers/linq-to-xml-dynamic-properties).</span></span> <span data-ttu-id="45c8f-110">Обратите внимание на то, что объявление пространства имен по умолчанию для XML не применяется к именам атрибутов.</span><span class="sxs-lookup"><span data-stu-id="45c8f-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 <span data-ttu-id="45c8f-111">Следующий код вызывает C# <xref:System.Xml.Linq.XDocument.Load%2A> и задает контекст данных панели стека для всех подэлементов элемента с именем `SolarSystemPlanets` в `http://planetsNS` пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="45c8f-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 <span data-ttu-id="45c8f-112">XML-данные можно сохранить в качестве ресурсов XAML с помощью <xref:System.Windows.Data.ObjectDataProvider>.</span><span class="sxs-lookup"><span data-stu-id="45c8f-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="45c8f-113">Полный пример см. в разделе [Исходный код L2DBForm.xaml](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e).</span><span class="sxs-lookup"><span data-stu-id="45c8f-113">For a complete example, see  [L2DBForm.xaml Source Code](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e).</span></span> <span data-ttu-id="45c8f-114">В следующем примере показано, каким образом код может задавать контекст данных для ресурса объекта.</span><span class="sxs-lookup"><span data-stu-id="45c8f-114">The following sample shows how code can set the data context to an object resource.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <span data-ttu-id="45c8f-115">Динамические свойства, которые сопоставляются с <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> обеспечивают гибкость в XAML.</span><span class="sxs-lookup"><span data-stu-id="45c8f-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="45c8f-116">Код также можно привязать к результатам запроса LINQ для XML.</span><span class="sxs-lookup"><span data-stu-id="45c8f-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="45c8f-117">В этом примере он привязывается к результатам запроса, направленного значением элемента.</span><span class="sxs-lookup"><span data-stu-id="45c8f-117">This example binds to query results ordered by an element value.</span></span>  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a><span data-ttu-id="45c8f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="45c8f-118">See Also</span></span>  
 [<span data-ttu-id="45c8f-119">Общие сведения об источниках привязки</span><span class="sxs-lookup"><span data-stu-id="45c8f-119">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="45c8f-120">Общие сведения о привязке данных WPF с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="45c8f-120">WPF Data Binding with LINQ to XML Overview</span></span>](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [<span data-ttu-id="45c8f-121">Привязка данных WPF с использованием примера LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="45c8f-121">WPF Data Binding Using LINQ to XML Example</span></span>](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)  
 [<span data-ttu-id="45c8f-122">Динамические свойства LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="45c8f-122">LINQ to XML Dynamic Properties</span></span>](/visualstudio/designers/linq-to-xml-dynamic-properties)
