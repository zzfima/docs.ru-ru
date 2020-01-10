---
title: Нахождение элемента автоматизации пользовательского интерфейса для элемента списка
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2474edf95bf598ba9284b5f6ac36a9e0af1317a1
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741757"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="cb1e5-102">Нахождение элемента автоматизации пользовательского интерфейса для элемента списка</span><span class="sxs-lookup"><span data-stu-id="cb1e5-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="cb1e5-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="cb1e5-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cb1e5-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="cb1e5-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="cb1e5-105">В этом разделе показано, как получить <xref:System.Windows.Automation.AutomationElement> для элемента в списке, если известен индекс элемента.</span><span class="sxs-lookup"><span data-stu-id="cb1e5-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb1e5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="cb1e5-106">Example</span></span>  
 <span data-ttu-id="cb1e5-107">В следующем примере показаны два способа получения указанного элемента из списка, один из которых использует <xref:System.Windows.Automation.TreeWalker>, а другой — с помощью <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb1e5-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="cb1e5-108">Первый способ, как правило, будет быстрее для элементов управления Win32, а второй — быстрее для элементов управления Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="cb1e5-108">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="cb1e5-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="cb1e5-109">See also</span></span>

- [<span data-ttu-id="cb1e5-110">Получение элементов модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="cb1e5-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
