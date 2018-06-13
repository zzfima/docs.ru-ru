---
title: Практическое руководство. Привязка графического элемента к элементу
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: fb419ee5a57e81e7e3bc72ae04fd200703b80cd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552556"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="9924b-102">Практическое руководство. Привязка графического элемента к элементу</span><span class="sxs-lookup"><span data-stu-id="9924b-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="9924b-103">В этом примере показано, как программным способом привязки графического элемента с заданным <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="9924b-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9924b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9924b-104">Example</span></span>  
 <span data-ttu-id="9924b-105">Для привязки к конкретному графический элемент <xref:System.Windows.UIElement>, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9924b-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9924b-106">Вызовите `static` метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> для получения <xref:System.Windows.Documents.AdornerLayer> для объекта <xref:System.Windows.UIElement> оформляемого.</span><span class="sxs-lookup"><span data-stu-id="9924b-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="9924b-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> перемещается вверх по дереву visual, начиная с указанного **UIElement**и возвращает первый слой графических элементов, которые найдет.</span><span class="sxs-lookup"><span data-stu-id="9924b-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="9924b-108">(Если слои декоративных элементов не найдены, метод возвращает значение 0.)</span><span class="sxs-lookup"><span data-stu-id="9924b-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="9924b-109">Вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки к целевому декоратора **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="9924b-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="9924b-110">Следующий пример привязывает (показано выше) для SimpleCircleAdorner <xref:System.Windows.Controls.TextBox> с именем *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="9924b-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="9924b-111">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9924b-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9924b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9924b-112">See Also</span></span>  
 [<span data-ttu-id="9924b-113">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="9924b-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
