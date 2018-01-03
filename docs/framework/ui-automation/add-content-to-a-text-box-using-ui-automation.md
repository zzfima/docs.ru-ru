---
title: "Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса"
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
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: be0081bc830a2995f7cba9f2a080c6ee33dcc79a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="dc53f-102">Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="dc53f-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="dc53f-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="dc53f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dc53f-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="dc53f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="dc53f-105">В этом разделе содержится пример кода, который демонстрирует использование [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для вставки текста в однострочное текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="dc53f-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="dc53f-106">Альтернативный метод предоставляется для элементов управления многострочного текста и форматированный текст где [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] не применяется.</span><span class="sxs-lookup"><span data-stu-id="dc53f-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="dc53f-107">Для сравнения в примере также показано использование методов Win32 для получения таких же результатов.</span><span class="sxs-lookup"><span data-stu-id="dc53f-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc53f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="dc53f-108">Example</span></span>  
 <span data-ttu-id="dc53f-109">Следующий пример проходит через последовательность текстовых элементов управления в целевом приложении.</span><span class="sxs-lookup"><span data-stu-id="dc53f-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="dc53f-110">Каждый текстовый элемент управления проверяется на предмет <xref:System.Windows.Automation.ValuePattern> объекта можно получить с помощью <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="dc53f-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="dc53f-111">Если текстовый элемент управления поддерживает <xref:System.Windows.Automation.ValuePattern>, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> метод используется для вставки пользовательской строкой в текстовом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="dc53f-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="dc53f-112">В противном случае <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> используется метод.</span><span class="sxs-lookup"><span data-stu-id="dc53f-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="dc53f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dc53f-113">See Also</span></span>  
 [<span data-ttu-id="dc53f-114">Пример текста TextPattern Insert</span><span class="sxs-lookup"><span data-stu-id="dc53f-114">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
