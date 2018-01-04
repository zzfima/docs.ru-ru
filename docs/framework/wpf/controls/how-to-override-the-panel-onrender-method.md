---
title: "Практическое руководство. Переопределение метода панели OnRender"
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 958595cdfa521b372270d6283c7134ef0ba0ef79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
