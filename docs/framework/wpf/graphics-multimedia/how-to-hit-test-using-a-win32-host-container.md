---
title: Практическое руководство. Проверка попадания курсора с помощью вложенного контейнера Win32
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: a86c1c36f75fa232d52731959371268a8b2593d7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452809"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="d3bdd-102">Практическое руководство. Проверка попадания курсора с помощью вложенного контейнера Win32</span><span class="sxs-lookup"><span data-stu-id="d3bdd-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="d3bdd-103">Визуальные объекты можно создавать в окне Win32, предоставляя контейнер главного окна для визуальных объектов.</span><span class="sxs-lookup"><span data-stu-id="d3bdd-103">You can create visual objects within a Win32 window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="d3bdd-104">Чтобы обрабатывать события для содержащихся визуальных объектов, выполняется обработка сообщений, переданных в цикл фильтрации сообщений контейнера окна.</span><span class="sxs-lookup"><span data-stu-id="d3bdd-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="d3bdd-105">Дополнительные сведения о размещении визуальных объектов в окне Win32 см. в разделе [учебник. размещение визуальных объектов в приложении Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) .</span><span class="sxs-lookup"><span data-stu-id="d3bdd-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a Win32 window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3bdd-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d3bdd-106">Example</span></span>  
 <span data-ttu-id="d3bdd-107">В следующем коде показано, как настроить обработчики событий мыши для окна Win32, которое используется в качестве контейнера размещения для визуальных объектов.</span><span class="sxs-lookup"><span data-stu-id="d3bdd-107">The following code shows how to set up mouse event handlers for a Win32 window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="d3bdd-108">В следующем примере показано, как настроить проверку нажатия в ответ на перехват конкретных событий мыши.</span><span class="sxs-lookup"><span data-stu-id="d3bdd-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="d3bdd-109">Объект <xref:System.Windows.Interop.HwndSource> представляет содержимое [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] в окне Win32.</span><span class="sxs-lookup"><span data-stu-id="d3bdd-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a Win32 window.</span></span> <span data-ttu-id="d3bdd-110">Значение свойства <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объекта <xref:System.Windows.Interop.HwndSource> представляет самый верхний узел в иерархии визуального дерева.</span><span class="sxs-lookup"><span data-stu-id="d3bdd-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="d3bdd-111">Полный пример проверки попадания объектов с помощью контейнера узлов Win32 см. в разделе [Проверка попадания с использованием примера взаимодействия Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span><span class="sxs-lookup"><span data-stu-id="d3bdd-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bdd-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d3bdd-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="d3bdd-113">Проверка нажатия на визуальном уровне</span><span class="sxs-lookup"><span data-stu-id="d3bdd-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="d3bdd-114">Руководство по размещению визуальных объектов в приложении Win32</span><span class="sxs-lookup"><span data-stu-id="d3bdd-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
