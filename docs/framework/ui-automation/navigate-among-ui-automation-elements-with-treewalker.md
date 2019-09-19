---
title: Навигация между элементами автоматизированного пользовательского интерфейса с помощью TreeWalker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: 7ecf6edd37b656f7dd1d7e31506d0dd455592d9b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042978"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="f3994-102">Навигация между элементами автоматизированного пользовательского интерфейса с помощью TreeWalker</span><span class="sxs-lookup"><span data-stu-id="f3994-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="f3994-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="f3994-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f3994-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f3994-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f3994-105">В этом разделе содержится пример кода, демонстрирующий навигацию [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] между элементами с <xref:System.Windows.Automation.TreeWalker> помощью класса.</span><span class="sxs-lookup"><span data-stu-id="f3994-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3994-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f3994-106">Example</span></span>  
 <span data-ttu-id="f3994-107">В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetParent%2A> для прохода по [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] дереву до тех пор, пока не будет найден корневой элемент или Рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="f3994-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="f3994-108">Элемент, расположенный ниже, является родительским окном указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="f3994-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="f3994-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f3994-109">Example</span></span>  
 <span data-ttu-id="f3994-110">В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> и <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> для создания объекта <xref:System.Windows.Forms.TreeView> , который показывает все поддерево [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элементов, которые находятся в представлении элемента управления и включены.</span><span class="sxs-lookup"><span data-stu-id="f3994-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="f3994-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f3994-111">See also</span></span>

- [<span data-ttu-id="f3994-112">Получение элементов модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="f3994-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
