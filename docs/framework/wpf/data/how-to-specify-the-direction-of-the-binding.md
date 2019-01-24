---
title: Как выполнить Указание направления привязки
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 6e617b2fdb6150aa8d5d6960f7aab58198c8b240
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550153"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Как выполнить Указание направления привязки
В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.  
  
## <a name="example"></a>Пример  
 Использовании <xref:System.Windows.Data.Binding.Mode%2A> свойство, чтобы указать направление привязки. В следующем списке перечислены доступные параметры для обновлений привязки.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> обновляет свойство цели или свойство, при каждом изменении целевого свойства или свойства источника.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> обновляет свойство цели только при изменении свойства источника.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime> обновляет свойство цели только при запуске приложения или при <xref:System.Windows.FrameworkElement.DataContext%2A> подвергается изменению.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> Обновляет свойство источника при изменении свойства цели.  
  
-   <xref:System.Windows.Data.BindingMode.Default> по умолчанию <xref:System.Windows.Data.Binding.Mode%2A> значение целевого свойства для использования.  
  
 Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Для обнаружения изменений в источнике (применимо к <xref:System.Windows.Data.BindingMode.OneWay> и <xref:System.Windows.Data.BindingMode.TwoWay> привязок), источник должен реализовывать механизм уведомлений об изменениях соответствующее свойство <xref:System.ComponentModel.INotifyPropertyChanged>. См. в разделе [реализация уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) пример <xref:System.ComponentModel.INotifyPropertyChanged> реализации.  
  
 Для <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource> привязок, можно управлять временем обновлений источника, задав <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойство. Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Data.Binding>
- [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
