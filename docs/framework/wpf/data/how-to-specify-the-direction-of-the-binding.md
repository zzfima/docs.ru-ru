---
title: Практическое руководство. Указание направления привязки
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459095"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Как указать направление привязки

В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.  
  
## <a name="example"></a>Пример  
 Для указания направления привязки используется свойство <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType>. Ниже приведены доступные варианты обновления привязок.  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> обновляет целевое свойство или свойство, когда изменяется либо свойство Target, либо свойство Source.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> обновляет свойство цели только при изменении свойства Source.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> обновляет целевое свойство только при запуске приложения или при изменении <xref:System.Windows.FrameworkElement.DataContext%2A>.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> обновляет свойство источника при изменении целевого свойства.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> вызывает использование <xref:System.Windows.Data.Binding.Mode%2A> значения по умолчанию для целевого свойства.  
  
 Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Чтобы обнаружить изменения источника (применимые к привязкам <xref:System.Windows.Data.BindingMode.OneWay> и <xref:System.Windows.Data.BindingMode.TwoWay>), источник должен реализовать подходящий механизм уведомления об изменении свойств, например <xref:System.ComponentModel.INotifyPropertyChanged>. Пример реализации <xref:System.ComponentModel.INotifyPropertyChanged> см. в разделе Реализация [уведомления об изменении свойства](how-to-implement-property-change-notification.md) .  
  
 Для <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource>ных привязок можно управлять временем обновления источника, установив свойство <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>. Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.Binding>
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
