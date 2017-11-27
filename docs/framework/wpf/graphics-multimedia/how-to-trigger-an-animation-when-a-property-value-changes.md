---
title: "Практическое руководство. Запуск анимации при изменении значения свойства"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d722be0f0367f7e6e98ef1c8451ce58ee28fedd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Практическое руководство. Запуск анимации при изменении значения свойства
В этом примере показано, как использовать <xref:System.Windows.Trigger> запуск <xref:System.Windows.Media.Animation.Storyboard> при изменении значения свойства. Можно использовать <xref:System.Windows.Trigger> внутри <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, или <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Trigger> для анимации <xref:System.Windows.UIElement.Opacity%2A> из <xref:System.Windows.Controls.Button> при его <xref:System.Windows.UIElement.IsMouseOver%2A> свойство становится `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Анимации с помощью свойства <xref:System.Windows.Trigger> объекты ведут себя в сложнее, чем <xref:System.Windows.EventTrigger> анимации или анимации работы с использованием <xref:System.Windows.Media.Animation.Storyboard> методов.  Они «передаваться» с анимацией определенные другими <xref:System.Windows.Trigger> объектов, но объединено <xref:System.Windows.EventTrigger> и запустить метод анимации.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Trigger>  
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
