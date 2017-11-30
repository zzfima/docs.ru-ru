---
title: "Навигация между элементами автоматизированного пользовательского интерфейса с помощью TreeWalker"
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
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
caps.latest.revision: "8"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 3f237184cb4364b90d8a16cd078faeaec62bb693
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="0d807-102">Навигация между элементами автоматизированного пользовательского интерфейса с помощью TreeWalker</span><span class="sxs-lookup"><span data-stu-id="0d807-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
>  <span data-ttu-id="0d807-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="0d807-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0d807-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="0d807-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="0d807-105">В этом разделе содержится пример кода, иллюстрирующий переход между [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элементов с помощью <xref:System.Windows.Automation.TreeWalker> класса.</span><span class="sxs-lookup"><span data-stu-id="0d807-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d807-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0d807-106">Example</span></span>  
 <span data-ttu-id="0d807-107">В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetParent%2A> стека для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] дерева, пока не будет найден корневой элемент или рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="0d807-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="0d807-108">За ним элемент является родительским окном указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="0d807-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="0d807-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0d807-109">Example</span></span>  
 <span data-ttu-id="0d807-110">В следующем примере используется <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> и <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> для создания <xref:System.Windows.Forms.TreeView> , отображающий все поддерево [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элементов, находящихся в представлении элемента управления и включены.</span><span class="sxs-lookup"><span data-stu-id="0d807-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="0d807-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0d807-111">See Also</span></span>  
 [<span data-ttu-id="0d807-112">Получение элементов автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0d807-112">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
