---
title: Как выполнить Переопределение метода панели OnRender
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: bb2ccffd9eda46eff2c7ee098a5261fc8f128cab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702877"
---
# <a name="how-to-override-the-panel-onrender-method"></a>Как выполнить Переопределение метода панели OnRender
В этом примере показано, как переопределить <xref:System.Windows.Controls.Panel.OnRender%2A> метод <xref:System.Windows.Controls.Panel> для добавления пользовательских графических эффектов в элемент макета.  
  
## <a name="example"></a>Пример  
 Используйте <xref:System.Windows.Controls.Panel.OnRender%2A> метод для добавления графических эффектов к элементу отображаемой панели. Например этот метод можно использовать для добавления пользовательских границу или фон эффекты. Объект <xref:System.Windows.Media.DrawingContext> объект передается как аргумент, который предоставляет методы для рисования фигур, текста, изображений и видео. Таким образом этот метод полезен для настройки объекта панели.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Panel>
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Пример пользовательской радиальной панели](https://go.microsoft.com/fwlink/?LinkID=159982)
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
