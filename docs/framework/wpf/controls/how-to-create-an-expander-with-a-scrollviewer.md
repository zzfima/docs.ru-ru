---
title: Практическое руководство. Создание расширителя с элементом ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 6c014d4f6a12bfb58c2ae68f580f632c9478c82f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553066"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="fdf1c-102">Практическое руководство. Создание расширителя с элементом ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="fdf1c-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="fdf1c-103">В этом примере показано, как создать <xref:System.Windows.Controls.Expander> элемент управления, содержащий сложного содержимого, такие как изображение и текст.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="fdf1c-104">Пример также помещает содержимое <xref:System.Windows.Controls.Expander> в <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdf1c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="fdf1c-105">Example</span></span>  
 <span data-ttu-id="fdf1c-106">В следующем примере показано, как создать <xref:System.Windows.Controls.Expander>.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="fdf1c-107">В этом примере <xref:System.Windows.Controls.Primitives.BulletDecorator> управления, который содержит изображение и текст, чтобы определить <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="fdf1c-108">Объект <xref:System.Windows.Controls.ScrollViewer> управления предоставляет метод для прокрутки развернутого содержимого.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="fdf1c-109">Обратите внимание, что в этом примере <xref:System.Windows.FrameworkElement.Height%2A> свойство <xref:System.Windows.Controls.ScrollViewer> вместо доступа к содержимому.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="fdf1c-110">Если <xref:System.Windows.FrameworkElement.Height%2A> устанавливается с содержимым, <xref:System.Windows.Controls.ScrollViewer> не позволяет пользователю выполнять прокрутку содержимого.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="fdf1c-111"><xref:System.Windows.FrameworkElement.Width%2A> Установлено свойство <xref:System.Windows.Controls.Expander> управления и этот параметр применяется к <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и развернутого содержимого.</span><span class="sxs-lookup"><span data-stu-id="fdf1c-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="fdf1c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fdf1c-112">See Also</span></span>  
 <xref:System.Windows.Controls.Expander>  
 [<span data-ttu-id="fdf1c-113">Общие сведения о расширителе</span><span class="sxs-lookup"><span data-stu-id="fdf1c-113">Expander Overview</span></span>](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [<span data-ttu-id="fdf1c-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="fdf1c-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
