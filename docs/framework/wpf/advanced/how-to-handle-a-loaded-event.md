---
title: Практическое руководство. Обработка загруженного события
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: b8cd2f5e9d848cebb712e7b4930ca39efe48ecc0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122555"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="55144-102">Практическое руководство. Обработка загруженного события</span><span class="sxs-lookup"><span data-stu-id="55144-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="55144-103">В этом примере демонстрируется обработка <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> событий и соответствующий скрипт для обработки этого события.</span><span class="sxs-lookup"><span data-stu-id="55144-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="55144-104">Создает обработчик <xref:System.Windows.Controls.Button> при загрузке страницы.</span><span class="sxs-lookup"><span data-stu-id="55144-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55144-105">Пример</span><span class="sxs-lookup"><span data-stu-id="55144-105">Example</span></span>  
 <span data-ttu-id="55144-106">В следующем примере используется [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] вместе с файлом кода.</span><span class="sxs-lookup"><span data-stu-id="55144-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="55144-107">См. также</span><span class="sxs-lookup"><span data-stu-id="55144-107">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- [<span data-ttu-id="55144-108">События времени жизни объекта</span><span class="sxs-lookup"><span data-stu-id="55144-108">Object Lifetime Events</span></span>](object-lifetime-events.md)
- [<span data-ttu-id="55144-109">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="55144-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="55144-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="55144-110">How-to Topics</span></span>](base-elements-how-to-topics.md)
