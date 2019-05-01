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
ms.openlocfilehash: afecb87dcfce1a8c48f1b2108edeae3cfd2aa16f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020963"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="5ce22-102">Практическое руководство. Привязка к XDocument, XElement или LINQ для результатов запросов XML</span><span class="sxs-lookup"><span data-stu-id="5ce22-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>
<span data-ttu-id="5ce22-103">В этом примере показано, как привязать данные XML <xref:System.Windows.Controls.ItemsControl> с помощью <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="5ce22-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ce22-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5ce22-104">Example</span></span>  
 <span data-ttu-id="5ce22-105">Следующий код XAML определяет <xref:System.Windows.Controls.ItemsControl> и включает в себя шаблон данных для данных типа `Planet` в `http://planetsNS` пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="5ce22-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="5ce22-106">Тип данных XML, заполняющий пространство имен, должен включать пространство имен, заключенное в фигурные скобки, или (при отображении вместе с расширением разметки XAML) предшествовать пространству имен с escape-последовательностью в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="5ce22-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="5ce22-107">Этот код привязывается к динамическим свойствам, которые соответствуют <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> методы <xref:System.Xml.Linq.XElement> класса.</span><span class="sxs-lookup"><span data-stu-id="5ce22-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="5ce22-108">Динамические свойства включают XAML для привязки к динамическим свойствам, предоставляющим доступ к именам методов.</span><span class="sxs-lookup"><span data-stu-id="5ce22-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="5ce22-109">Дополнительные сведения см. в разделе [Динамические свойства LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties).</span><span class="sxs-lookup"><span data-stu-id="5ce22-109">To learn more, see [LINQ to XML Dynamic Properties](/visualstudio/designers/linq-to-xml-dynamic-properties).</span></span> <span data-ttu-id="5ce22-110">Обратите внимание на то, что объявление пространства имен по умолчанию для XML не применяется к именам атрибутов.</span><span class="sxs-lookup"><span data-stu-id="5ce22-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>  
  
 [!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 <span data-ttu-id="5ce22-111">Следующие вызовы кода C# <xref:System.Xml.Linq.XDocument.Load%2A> и задает контекст данных панели стека для всех подэлементов элемента с именем `SolarSystemPlanets` в `http://planetsNS` пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="5ce22-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 <span data-ttu-id="5ce22-112">XML-данные могут храниться в виде ресурсов XAML с помощью <xref:System.Windows.Data.ObjectDataProvider>.</span><span class="sxs-lookup"><span data-stu-id="5ce22-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="5ce22-113">Полный пример см. в разделе [исходный код L2DBForm.xaml](/visualstudio/designers/l2dbform-xaml-source-code).</span><span class="sxs-lookup"><span data-stu-id="5ce22-113">For a complete example, see  [L2DBForm.xaml source code](/visualstudio/designers/l2dbform-xaml-source-code).</span></span> <span data-ttu-id="5ce22-114">В следующем примере показано, каким образом код может задавать контекст данных для ресурса объекта.</span><span class="sxs-lookup"><span data-stu-id="5ce22-114">The following sample shows how code can set the data context to an object resource.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <span data-ttu-id="5ce22-115">Динамические свойства, которые сопоставляются с <xref:System.Xml.Linq.XContainer.Element%2A> и <xref:System.Xml.Linq.XElement.Attribute%2A> обеспечивают гибкость в XAML.</span><span class="sxs-lookup"><span data-stu-id="5ce22-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="5ce22-116">Код также можно привязать к результатам запроса LINQ для XML.</span><span class="sxs-lookup"><span data-stu-id="5ce22-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="5ce22-117">В этом примере он привязывается к результатам запроса, направленного значением элемента.</span><span class="sxs-lookup"><span data-stu-id="5ce22-117">This example binds to query results ordered by an element value.</span></span>  
  
 [!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a><span data-ttu-id="5ce22-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5ce22-118">See also</span></span>

- [<span data-ttu-id="5ce22-119">Общие сведения об источниках привязки</span><span class="sxs-lookup"><span data-stu-id="5ce22-119">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="5ce22-120">Общие сведения о привязке данных WPF с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="5ce22-120">WPF Data Binding with LINQ to XML Overview</span></span>](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [<span data-ttu-id="5ce22-121">Привязка данных WPF с использованием примера LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="5ce22-121">WPF Data Binding Using LINQ to XML Example</span></span>](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)
- [<span data-ttu-id="5ce22-122">Динамические свойства LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="5ce22-122">LINQ to XML Dynamic Properties</span></span>](/visualstudio/designers/linq-to-xml-dynamic-properties)
