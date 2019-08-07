---
title: Практическое руководство. Указание направления привязки
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 023cd42ad5fb321e7ffa65f08673cb4145f49af4
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817909"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Практическое руководство. Укажите направление привязки

В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> Свойство используется для указания направления привязки. Ниже приведены доступные варианты обновления привязок.  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>обновляет целевое свойство или свойство, когда изменяется либо свойство Target, либо свойство Source.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>обновляет свойство Target только при изменении свойства Source.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>обновляет целевое свойство только при запуске приложения или при <xref:System.Windows.FrameworkElement.DataContext%2A> изменении.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType>обновляет свойство Source при изменении целевого свойства.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>вызывает использование значения <xref:System.Windows.Data.Binding.Mode%2A> по умолчанию целевого свойства.  
  
 Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Для обнаружения изменений источника (применимо <xref:System.Windows.Data.BindingMode.OneWay> к <xref:System.Windows.Data.BindingMode.TwoWay> привязкам и) источник должен реализовать подходящий механизм уведомления об <xref:System.ComponentModel.INotifyPropertyChanged>изменении свойств, например. Пример<xref:System.ComponentModel.INotifyPropertyChanged> реализации см. в разделе [Реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md) .  
  
 Для <xref:System.Windows.Data.BindingMode.TwoWay> привязок или <xref:System.Windows.Data.BindingMode.OneWayToSource> можно управлять временем обновлений <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> источника, задав свойство. Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.Binding>
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
