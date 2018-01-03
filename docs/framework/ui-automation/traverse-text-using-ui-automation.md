---
title: "Проход по тексту при помощи модели автоматизации пользовательского интерфейса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: fadeb1cff4956b6be8ae01c8a9ffa911772514cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="07669-102">Проход по тексту при помощи модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="07669-102">Traverse Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="07669-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="07669-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="07669-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="07669-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="07669-105">В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для перехода по текстовому содержимому документа шагами приращения <xref:System.Windows.Automation.Text.TextUnit> .</span><span class="sxs-lookup"><span data-stu-id="07669-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07669-106">Пример</span><span class="sxs-lookup"><span data-stu-id="07669-106">Example</span></span>  
 <span data-ttu-id="07669-107">В следующем примере кода показано, как проходить содержимое поставщика текста автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="07669-107">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="07669-108">Метод <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> перемещает конечные точки <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> и <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> диапазона <xref:System.Windows.Automation.Text.TextPatternRange>.</span><span class="sxs-lookup"><span data-stu-id="07669-108">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="07669-109">Этот диапазон текста обычно является вырожденным диапазоном, представляющим точку вставки текста.</span><span class="sxs-lookup"><span data-stu-id="07669-109">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07669-110">Поскольку только основанные на тексте внедренные объекты считаются частью текстового потока, такие внедренные объекты, как изображения, не влияют на `Move` или его возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="07669-110">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="07669-111">Любой метод, использующий <xref:System.Windows.Automation.Text.TextUnit> , будет откладываться для следующего наибольшего <xref:System.Windows.Automation.Text.TextUnit> , поддерживаемого если указанный <xref:System.Windows.Automation.Text.TextUnit> не поддерживается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="07669-111">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07669-112">См. также</span><span class="sxs-lookup"><span data-stu-id="07669-112">See Also</span></span>  
 [<span data-ttu-id="07669-113">Общие сведения об объекте TextPattern модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="07669-113">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="07669-114">Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="07669-114">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="07669-115">Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="07669-115">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [<span data-ttu-id="07669-116">Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="07669-116">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="07669-117">Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов</span><span class="sxs-lookup"><span data-stu-id="07669-117">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
