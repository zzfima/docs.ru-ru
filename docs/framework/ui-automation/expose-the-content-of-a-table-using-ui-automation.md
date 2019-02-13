---
title: Представление содержимого таблицы с помощью автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables, exposing content of
- UI Automation, exposing content of tables
- exposing content of tables using UI Automation
ms.assetid: ac3c5eaa-49c7-4653-b83e-532e2a2604a2
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 2145888b76077056988652418fd1eab878348258
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219351"
---
# <a name="expose-the-content-of-a-table-using-ui-automation"></a><span data-ttu-id="5be68-102">Представление содержимого таблицы с помощью автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5be68-102">Expose the Content of a Table Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="5be68-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="5be68-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5be68-104">Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5be68-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5be68-105">В этом разделе показано, как [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] может использоваться для представления содержимого и внутренних свойств каждой ячейки табличного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5be68-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose the content and intrinsic properties of each cell within a tabular control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5be68-106">Пример</span><span class="sxs-lookup"><span data-stu-id="5be68-106">Example</span></span>  
 <span data-ttu-id="5be68-107">В следующем примере кода демонстрируется получение <xref:System.Windows.Automation.AutomationElement> , представляющий содержимое ячейки таблицы; также получаются свойства ячеек, например индексы строки и столбца, диапазонов строк и столбцов и строк и столбцов данных в заголовке.</span><span class="sxs-lookup"><span data-stu-id="5be68-107">The following code example demonstrates how to obtain a <xref:System.Windows.Automation.AutomationElement> that represents the content of a table cell; cell properties such as row and column indices, row and column spans, and row and column header information are also obtained.</span></span> <span data-ttu-id="5be68-108">В этом примере используется обработчик событий изменения фокуса для имитации прохождения клавиатуры табличного элемента управления, реализующий [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5be68-108">This example uses a focus change event handler to simulate keyboard traversal of a tabular control that implements [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5be68-109">Сведения для каждого элемента таблицы предоставляются на событие изменения фокуса.</span><span class="sxs-lookup"><span data-stu-id="5be68-109">Information for each table item is exposed on a focus change event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5be68-110">Так как изменения фокуса глобальные события рабочего стола, события изменения фокуса вне таблицы должны быть отфильтрованы.</span><span class="sxs-lookup"><span data-stu-id="5be68-110">Since focus changes are global desktop events, focus change events outside the table should be filtered.</span></span> <span data-ttu-id="5be68-111">См. в разделе [реализации](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) для соответствующей реализации.</span><span class="sxs-lookup"><span data-stu-id="5be68-111">See the [TrackFocus Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) for a related implementation.</span></span>  
  
 [!code-csharp[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#starttarget)]
 [!code-vb[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#starttarget)]  
[!code-csharp[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#gettableelement)]
[!code-vb[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#gettableelement)]  
[!code-csharp[UIATableItemPattern_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#101)]
[!code-vb[UIATableItemPattern_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#101)]  
[!code-csharp[UIATableItemPattern_snip#1015](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#1015)]
[!code-vb[UIATableItemPattern_snip#1015](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#1015)]  
[!code-csharp[UIATableItemPattern_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#102)]
[!code-vb[UIATableItemPattern_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#102)]  
[!code-csharp[UIATableItemPattern_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#103)]
[!code-vb[UIATableItemPattern_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="5be68-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5be68-112">See also</span></span>
- [<span data-ttu-id="5be68-113">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5be68-113">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="5be68-114">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="5be68-114">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="5be68-115">Реализация шаблона элемента управления Table модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5be68-115">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="5be68-116">Реализация шаблона элемента управления TableItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5be68-116">Implementing the UI Automation TableItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="5be68-117">Реализация шаблона элемента управления Grid модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5be68-117">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="5be68-118">Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5be68-118">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)
