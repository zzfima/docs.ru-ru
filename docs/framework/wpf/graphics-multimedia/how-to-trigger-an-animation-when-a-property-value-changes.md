---
title: Как выполнить Запуск анимации при изменении значения свойства
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 2be85a9ae93d504d98930468ad2e257385e835f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705301"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Как выполнить Запуск анимации при изменении значения свойства
В этом примере показано, как использовать <xref:System.Windows.Trigger> запустить <xref:System.Windows.Media.Animation.Storyboard> при изменении значения свойства. Можно использовать <xref:System.Windows.Trigger> внутри <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, или <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Trigger> для анимации <xref:System.Windows.UIElement.Opacity%2A> из <xref:System.Windows.Controls.Button> при его <xref:System.Windows.UIElement.IsMouseOver%2A> свойство становится `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Анимации с помощью свойства <xref:System.Windows.Trigger> объекты ведут себя в сложнее, чем <xref:System.Windows.EventTrigger> анимации или анимации к использованию <xref:System.Windows.Media.Animation.Storyboard> методы.  Они «переходной» с анимацией определены другими <xref:System.Windows.Trigger> объектов, но compose с <xref:System.Windows.EventTrigger> и анимациями, запускаемыми.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Trigger>
- [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
- [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
