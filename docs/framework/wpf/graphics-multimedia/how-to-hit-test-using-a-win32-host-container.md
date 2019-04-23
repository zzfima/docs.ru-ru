---
title: Практическое руководство. Проверка попадания с использованием контейнера узла Win32
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: ac5cae5bcd94dc8bf80ff95b8971914e1fa5ba2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081467"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="ac5e1-102">Практическое руководство. Проверка попадания с использованием контейнера узла Win32</span><span class="sxs-lookup"><span data-stu-id="ac5e1-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="ac5e1-103">Можно создать визуальные объекты в пределах [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] окно путем предоставления контейнера окна для визуальных объектов.</span><span class="sxs-lookup"><span data-stu-id="ac5e1-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="ac5e1-104">Чтобы обрабатывать события для содержащихся визуальных объектов, выполняется обработка сообщений, переданных в цикл фильтрации сообщений контейнера окна.</span><span class="sxs-lookup"><span data-stu-id="ac5e1-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="ac5e1-105">Ссылаться на [руководства: По размещению визуальных объектов в приложении Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) Дополнительные сведения о способах размещения визуальных объектов в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна.</span><span class="sxs-lookup"><span data-stu-id="ac5e1-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac5e1-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ac5e1-106">Example</span></span>  
 <span data-ttu-id="ac5e1-107">Ниже показано, как настроить обработчики событий мыши для [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно, которое используется как контейнер для визуальных объектов.</span><span class="sxs-lookup"><span data-stu-id="ac5e1-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="ac5e1-108">Приведенный ниже показано, как настроить проверку нажатия в ответ на перехват определенных событий мыши.</span><span class="sxs-lookup"><span data-stu-id="ac5e1-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="ac5e1-109"><xref:System.Windows.Interop.HwndSource> Объект представляет [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимого в пределах [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] окна.</span><span class="sxs-lookup"><span data-stu-id="ac5e1-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="ac5e1-110">Значение <xref:System.Windows.Interop.HwndSource.RootVisual%2A> свойство <xref:System.Windows.Interop.HwndSource> представляет верхний узел в иерархии визуального дерева.</span><span class="sxs-lookup"><span data-stu-id="ac5e1-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="ac5e1-111">Полный пример проверки попадания объектов с помощью контейнера Win32 см. в разделе [проверка нажатия с помощью примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995).</span><span class="sxs-lookup"><span data-stu-id="ac5e1-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5e1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ac5e1-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="ac5e1-113">Проверка нажатия на визуальном уровне</span><span class="sxs-lookup"><span data-stu-id="ac5e1-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="ac5e1-114">Учебник. Руководство по размещению визуальных объектов в приложении Win32</span><span class="sxs-lookup"><span data-stu-id="ac5e1-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
