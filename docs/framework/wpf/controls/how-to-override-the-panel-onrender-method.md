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
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666707"
---
# <a name="how-to-override-the-panel-onrender-method"></a>Практическое руководство. Переопределение метода панели OnRender
В этом примере показано, как переопределить <xref:System.Windows.Controls.Panel.OnRender%2A> метод, <xref:System.Windows.Controls.Panel> чтобы добавить пользовательские графические эффекты в элемент макета.  
  
## <a name="example"></a>Пример  
 Используйте метод <xref:System.Windows.Controls.Panel.OnRender%2A> , чтобы добавить графические эффекты в отображаемый элемент Panel. Например, этот метод можно использовать для добавления пользовательской границы или фонового эффекта. <xref:System.Windows.Media.DrawingContext> Объект передается в качестве аргумента, который предоставляет методы для рисования фигур, текста, изображений или видео. В результате этот метод полезен для настройки объекта Panel.  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Panel>
- [Общие сведения о панелях](panels-overview.md)
- [Разделы практического руководства](panel-how-to-topics.md)
