---
title: Практическое руководство. Создание объекта, следующего за указателем мыши
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005063"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Практическое руководство. Создание объекта, следующего за указателем мыши
В этом примере показано, как изменить размеры объекта при перемещении указателя мыши на экран.  
  
 Пример включает файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], который создает [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], и файл кода программной части, который создает обработчик событий.  
  
## <a name="example"></a>Пример  
 Следующий код XAML создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который состоит из <xref:System.Windows.Shapes.Ellipse> внутри <xref:System.Windows.Controls.StackPanel> и присоединяет обработчик событий для события <xref:System.Windows.UIElement.MouseMove>.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Следующий программный код создает обработчик событий <xref:System.Windows.UIElement.MouseMove>.  При перемещении указателя мыши высота и ширина <xref:System.Windows.Shapes.Ellipse> увеличиваются и уменьшаются.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о входных данных](input-overview.md)
