---
title: Как выполнить Создание объекта, следующего за указателем мыши
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 3e39b9459fbc94c9b7684ffd7c597363e46ad717
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541824"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Как выполнить Создание объекта, следующего за указателем мыши
В этом примере показано, как изменить размеры объекта, при перемещении указателя мыши на экране.  
  
 В примере [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл, который создает [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] и файл кода, который создает обработчик событий.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который состоит из <xref:System.Windows.Shapes.Ellipse> внутри <xref:System.Windows.Controls.StackPanel>и присоединяет обработчик событий для <xref:System.Windows.UIElement.MouseMove> событий.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Следующий код создает <xref:System.Windows.UIElement.MouseMove> обработчик событий.  При перемещении указателя мыши, высоту и ширину <xref:System.Windows.Shapes.Ellipse> увеличиваются и уменьшаются.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)
