---
title: Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 71385690c01d261b4ff1b495674bab377232e81d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447258"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="88e70-102">Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="88e70-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="88e70-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="88e70-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="88e70-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="88e70-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="88e70-105">В этом разделе содержится пример кода, демонстрирующий использование [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для вставки текста в однострочное текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="88e70-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="88e70-106">Альтернативный метод предоставляется для многострочных и многофункциональных текстовых элементов управления, где [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] неприменимо.</span><span class="sxs-lookup"><span data-stu-id="88e70-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="88e70-107">Для сравнения в примере также демонстрируется использование методов Win32 для выполнения одинаковых результатов.</span><span class="sxs-lookup"><span data-stu-id="88e70-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88e70-108">Пример</span><span class="sxs-lookup"><span data-stu-id="88e70-108">Example</span></span>  
 <span data-ttu-id="88e70-109">В следующем примере выполняется пошаговая последовательность элементов управления текстом в целевом приложении.</span><span class="sxs-lookup"><span data-stu-id="88e70-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="88e70-110">Каждый элемент управления "текст" тестируется, чтобы узнать, можно ли получить объект <xref:System.Windows.Automation.ValuePattern> из него с помощью метода <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>.</span><span class="sxs-lookup"><span data-stu-id="88e70-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="88e70-111">Если элемент управления "текст" поддерживает <xref:System.Windows.Automation.ValuePattern>, метод <xref:System.Windows.Automation.ValuePattern.SetValue%2A> используется для вставки пользовательской строки в элемент управления Text.</span><span class="sxs-lookup"><span data-stu-id="88e70-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="88e70-112">В противном случае используется метод <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88e70-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="88e70-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="88e70-113">See also</span></span>

- <span data-ttu-id="88e70-114">[Пример вставки текста TextPattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="88e70-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>
