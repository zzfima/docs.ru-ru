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
ms.openlocfilehash: b71783f2d061c9139de4449d8e0106eb00345894
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740176"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Практическое руководство. Проверка попадания курсора с помощью вложенного контейнера Win32
Визуальные объекты можно создавать в окне Win32, предоставляя контейнер главного окна для визуальных объектов. Чтобы обрабатывать события для содержащихся визуальных объектов, выполняется обработка сообщений, переданных в цикл фильтрации сообщений контейнера окна. Дополнительные сведения о размещении визуальных объектов в окне Win32 см. в разделе [учебник. размещение визуальных объектов в приложении Win32](tutorial-hosting-visual-objects-in-a-win32-application.md) .  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как настроить обработчики событий мыши для окна Win32, которое используется в качестве контейнера размещения для визуальных объектов.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 В следующем примере показано, как настроить проверку нажатия в ответ на перехват конкретных событий мыши.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Объект <xref:System.Windows.Interop.HwndSource> представляет содержимое [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] в окне Win32. Значение свойства <xref:System.Windows.Interop.HwndSource.RootVisual%2A> объекта <xref:System.Windows.Interop.HwndSource> представляет самый верхний узел в иерархии визуального дерева.  
  
 Полный пример проверки попадания объектов с помощью контейнера узлов Win32 см. в разделе [Проверка попадания с использованием примера взаимодействия Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Interop.HwndSource>
- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
- [Руководство по размещению визуальных объектов в приложении Win32](tutorial-hosting-visual-objects-in-a-win32-application.md)
