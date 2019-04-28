---
title: Практическое руководство. Создание расширителя с элементом ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910797"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="9c37b-102">Практическое руководство. Создание расширителя с элементом ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="9c37b-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="9c37b-103">В этом примере показано, как создать <xref:System.Windows.Controls.Expander> элемент управления, который содержит сложное содержимое, например изображение и текст.</span><span class="sxs-lookup"><span data-stu-id="9c37b-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="9c37b-104">Пример также помещает содержимое <xref:System.Windows.Controls.Expander> в <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9c37b-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c37b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="9c37b-105">Example</span></span>  
 <span data-ttu-id="9c37b-106">В следующем примере показано, как создать <xref:System.Windows.Controls.Expander>.</span><span class="sxs-lookup"><span data-stu-id="9c37b-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="9c37b-107">В примере используется <xref:System.Windows.Controls.Primitives.BulletDecorator> управления, который содержит изображение и текст, чтобы определить <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c37b-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="9c37b-108">Объект <xref:System.Windows.Controls.ScrollViewer> управления предоставляет метод для прокрутки развернутого содержимого.</span><span class="sxs-lookup"><span data-stu-id="9c37b-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="9c37b-109">Обратите внимание, что в этом примере <xref:System.Windows.FrameworkElement.Height%2A> свойство <xref:System.Windows.Controls.ScrollViewer> вместо содержимого.</span><span class="sxs-lookup"><span data-stu-id="9c37b-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="9c37b-110">Если <xref:System.Windows.FrameworkElement.Height%2A> устанавливается на содержимом, <xref:System.Windows.Controls.ScrollViewer> не позволяет пользователю выполнять прокрутку содержимого.</span><span class="sxs-lookup"><span data-stu-id="9c37b-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="9c37b-111"><xref:System.Windows.FrameworkElement.Width%2A> Установлено свойство <xref:System.Windows.Controls.Expander> управления и этот параметр применяется к <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и развернутому содержимому.</span><span class="sxs-lookup"><span data-stu-id="9c37b-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="9c37b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9c37b-112">See also</span></span>

- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="9c37b-113">Общие сведения о расширителе</span><span class="sxs-lookup"><span data-stu-id="9c37b-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="9c37b-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="9c37b-114">How-to Topics</span></span>](expander-how-to-topics.md)
