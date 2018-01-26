---
title: "Практическое руководство. Проверка попадания курсора с помощью вложенного контейнера Win32"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 142c2faa01c32ac6602e80eaef18779f93154aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Практическое руководство. Проверка попадания курсора с помощью вложенного контейнера Win32
Можно создать визуальных объектов в пределах [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] окна использовать вложенный контейнер окна для визуальных объектов. Чтобы обрабатывать события для содержащихся визуальных объектов, выполняется обработка сообщений, переданных в цикл фильтрации сообщений контейнера окна. Ссылаться на [учебника: размещения визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) Дополнительные сведения о способах размещения визуальных объектов в [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окна.  
  
## <a name="example"></a>Пример  
 Ниже показано, как настройка обработчиков событий мыши для [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] окно, которое используется в качестве вложенного контейнера для визуальных объектов.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 В следующем примере показано, как для настройки проверки нажатия в ответ на перехват конкретных событий мыши.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource> Объект представляет [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимого в [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] окна. Значение <xref:System.Windows.Interop.HwndSource.RootVisual%2A> свойство <xref:System.Windows.Interop.HwndSource> представляет самый верхний узел в иерархии визуального дерева.  
  
 Полный пример проверки нажатия объектов с помощью вложенного контейнера Win32 см. в разделе [с образец взаимодействие Win32](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.HwndSource>  
 [Проверка нажатия на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Руководство по размещению визуальных объектов в приложении Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
