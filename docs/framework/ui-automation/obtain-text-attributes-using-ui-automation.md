---
title: Получение атрибутов текста с помощью UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
ms.openlocfilehash: c338f858f1715d23cad96919db4a21a6ba49710f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446910"
---
# <a name="obtain-text-attributes-using-ui-automation"></a><span data-ttu-id="b91d8-102">Получение атрибутов текста с помощью UI Automation</span><span class="sxs-lookup"><span data-stu-id="b91d8-102">Obtain Text Attributes Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="b91d8-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="b91d8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b91d8-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="b91d8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b91d8-105">В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для получения атрибутов текста из диапазона текста.</span><span class="sxs-lookup"><span data-stu-id="b91d8-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attributes from a text range.</span></span> <span data-ttu-id="b91d8-106">Диапазон текста может соответствовать текущему расположению курсора (или пустому выделению) в документе, связанному выделению текста, коллекции разрозненных выделений текста или всему текстовому содержимому документа.</span><span class="sxs-lookup"><span data-stu-id="b91d8-106">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b91d8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b91d8-107">Example</span></span>  
 <span data-ttu-id="b91d8-108">В следующем примере кода показано получение <xref:System.Windows.Automation.TextPattern.FontNameAttribute> из диапазона текста.</span><span class="sxs-lookup"><span data-stu-id="b91d8-108">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 <span data-ttu-id="b91d8-109">Шаблон элемента управления <xref:System.Windows.Automation.TextPattern> в сочетании с классом <xref:System.Windows.Automation.Text.TextPatternRange> поддерживает базовые текстовые атрибуты, свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="b91d8-109">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="b91d8-110">Для функциональности элемента управления, не поддерживаемой <xref:System.Windows.Automation.TextPattern> или <xref:System.Windows.Automation.Text.TextPatternRange> , класс <xref:System.Windows.Automation.AutomationElement>предоставляет клиенту автоматизации пользовательского интерфейса методы для доступа к соответствующей собственной объектной модели.</span><span class="sxs-lookup"><span data-stu-id="b91d8-110">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange> the <xref:System.Windows.Automation.AutomationElement>, class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91d8-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="b91d8-111">See also</span></span>

- [<span data-ttu-id="b91d8-112">Общие сведения об объекте TextPattern модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b91d8-112">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="b91d8-113">Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b91d8-113">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="b91d8-114">Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b91d8-114">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="b91d8-115">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b91d8-115">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="b91d8-116">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="b91d8-116">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="b91d8-117">Получение сведений об атрибутах смешанного текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b91d8-117">Obtain Mixed Text Attribute Details Using UI Automation</span></span>](obtain-mixed-text-attribute-details-using-ui-automation.md)
