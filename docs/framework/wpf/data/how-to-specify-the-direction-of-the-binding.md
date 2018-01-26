---
title: "Практическое руководство. Указание направления привязки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9944ff214a9dfe12b21e005c4e1998c249bf72b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Практическое руководство. Указание направления привязки
В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.  
  
## <a name="example"></a>Пример  
 Вы используете <xref:System.Windows.Data.Binding.Mode%2A> свойство, чтобы указать направление привязки. В следующем списке перечислены доступные параметры для обновлений привязки.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay>обновляет целевое свойство или свойства при каждом изменении целевого свойства или свойства source.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay>обновляет свойство целевого только при изменении свойства источника.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime>обновляет свойство целевого только в том случае, если приложение запускается или если <xref:System.Windows.FrameworkElement.DataContext%2A> меняется.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource>обновляет исходное свойство при изменении целевого свойства.  
  
-   <xref:System.Windows.Data.BindingMode.Default>по умолчанию <xref:System.Windows.Data.Binding.Mode%2A> значение целевого свойства для использования.  
  
 Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Для обнаружения изменений в источнике (применимо к <xref:System.Windows.Data.BindingMode.OneWay> и <xref:System.Windows.Data.BindingMode.TwoWay> привязок), источник должен применять механизм уведомлений об изменениях подходящего свойства <xref:System.ComponentModel.INotifyPropertyChanged>. В разделе [реализуют уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) пример <xref:System.ComponentModel.INotifyPropertyChanged> реализации.  
  
 Для <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource> привязки, задав может управлять временем обновлений источника <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойство. Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.Binding>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
