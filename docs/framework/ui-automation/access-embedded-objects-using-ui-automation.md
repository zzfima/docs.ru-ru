---
title: Доступ ко внедренным объектам с помощью автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
ms.openlocfilehash: 75c63360eab2cde95698bdaded5c5249a3ca89fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447267"
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="1e6f3-102">Доступ ко внедренным объектам с помощью автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6f3-102">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="1e6f3-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="1e6f3-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1e6f3-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="1e6f3-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="1e6f3-105">В этом разделе показано, как можно использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для представления объектов, внедренных в содержимое элемента управления "Текст".</span><span class="sxs-lookup"><span data-stu-id="1e6f3-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e6f3-106">Внедренные объекты могут включать изображения, гиперссылки, кнопки, таблицы или элементы ActiveX.</span><span class="sxs-lookup"><span data-stu-id="1e6f3-106">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="1e6f3-107">Внедренные объекты считаются дочерними элементами поставщика текста [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e6f3-107">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="1e6f3-108">Это позволяет предоставлять их через ту же древовидную структуру модели автоматизации пользовательского интерфейса, что и все остальные элементы [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e6f3-108">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="1e6f3-109">Функциональные возможности в свою очередь предоставляются с помощью шаблонов элементов управления, которые обычно требуются типом элемента управления внедренных объектов (например, поскольку гиперссылки основаны на тексте, они будут поддерживать <xref:System.Windows.Automation.TextPattern>).</span><span class="sxs-lookup"><span data-stu-id="1e6f3-109">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="1e6f3-110">![Embedded objects in a text container.](./media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="1e6f3-110">![Embedded objects in a text container.](./media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="1e6f3-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span><span class="sxs-lookup"><span data-stu-id="1e6f3-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e6f3-112">Пример</span><span class="sxs-lookup"><span data-stu-id="1e6f3-112">Example</span></span>  
 <span data-ttu-id="1e6f3-113">В следующем примере кода демонстрируется извлечение коллекции внедренных объектов из поставщика текста [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e6f3-113">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="1e6f3-114">Для образца документа, приведенного во введении, будет возвращено два объекта (элемент изображения и текстовый элемент).</span><span class="sxs-lookup"><span data-stu-id="1e6f3-114">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e6f3-115">Элемент изображения должен иметь некоторый связанный с ним встроенный текст, описывающий изображение, обычно в его свойстве <xref:System.Windows.Automation.AutomationElement.NameProperty> (например, "Синий кит".).</span><span class="sxs-lookup"><span data-stu-id="1e6f3-115">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="1e6f3-116">Однако если получен текстовый диапазон, перекрывающий этот объект-изображение, в текстовом потоке не возвращается ни это изображение, ни его описательный текст.</span><span class="sxs-lookup"><span data-stu-id="1e6f3-116">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="1e6f3-117">Пример</span><span class="sxs-lookup"><span data-stu-id="1e6f3-117">Example</span></span>  
 <span data-ttu-id="1e6f3-118">В следующем примере кода демонстрируется получение текстового диапазона из внедренного объекта в поставщике текста [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e6f3-118">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="1e6f3-119">Полученный текстовый диапазон является пустым диапазоном, где за начальной точкой следует "...</span><span class="sxs-lookup"><span data-stu-id="1e6f3-119">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="1e6f3-120">океан.(пространство)", и перед конечной точкой стоит закрывающая точка ".", представляющая внедренную гиперссылку (как показано на рисунке во введении).</span><span class="sxs-lookup"><span data-stu-id="1e6f3-120">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="1e6f3-121">Несмотря на то что это пустой диапазон, он не считается вырожденным диапазоном, так как содержит ненулевой промежуток.</span><span class="sxs-lookup"><span data-stu-id="1e6f3-121">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e6f3-122"><xref:System.Windows.Automation.TextPattern> может получить текстовый внедренный объект как гиперссылку; однако для предоставления полной функциональности внедренного объекта из него должен быть получен дополнительный <xref:System.Windows.Automation.TextPattern> .</span><span class="sxs-lookup"><span data-stu-id="1e6f3-122"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="1e6f3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1e6f3-123">See also</span></span>

- [<span data-ttu-id="1e6f3-124">Общие сведения об объекте TextPattern модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6f3-124">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="1e6f3-125">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6f3-125">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="1e6f3-126">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="1e6f3-126">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="1e6f3-127">Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6f3-127">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="1e6f3-128">Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="1e6f3-128">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
