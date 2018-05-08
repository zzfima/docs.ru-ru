---
title: Практическое руководство. Переопределение метода панели OnRender
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
ms.openlocfilehash: e591bc195d3b0ba58002bda42ddb3e9ed35d312e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-override-the-panel-onrender-method"></a>Практическое руководство. Переопределение метода панели OnRender
В этом примере показан способ переопределения <xref:System.Windows.Controls.Panel.OnRender%2A> метод <xref:System.Windows.Controls.Panel> для добавления пользовательских графических эффектов в элемент макета.  
  
## <a name="example"></a>Пример  
 Используйте <xref:System.Windows.Controls.Panel.OnRender%2A> метод для добавления графических эффектов в отображаемый элемент панели. Например этот метод можно использовать для добавления пользовательских границу или фон эффекты. Объект <xref:System.Windows.Media.DrawingContext> объект передается как аргумент, который предоставляет методы для рисования фигур, текст, изображения или видео. В результате этот метод полезен для настройки объекта панели.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Panel>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Пример пользовательской радиальной панели](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
