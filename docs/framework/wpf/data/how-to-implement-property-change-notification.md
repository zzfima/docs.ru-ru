---
title: Практическое руководство. Реализация уведомления об изменении свойства
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: a9c0fb433e2fa65e28db3b793e038b49f9d6353b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-property-change-notification"></a>Практическое руководство. Реализация уведомления об изменении свойства
Для поддержки <xref:System.Windows.Data.BindingMode.OneWay> или <xref:System.Windows.Data.BindingMode.TwoWay> привязки для включения в свойства целевого объекта привязки автоматически отражать динамические изменения источник привязки (например, область просмотра, обновляется автоматически, когда пользователь редактирует форму), класс необходимо предоставить соответствующие изменения свойств уведомления. В этом примере показано, как создать класс, реализующий <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## <a name="example"></a>Пример  
 Для реализации <xref:System.ComponentModel.INotifyPropertyChanged> необходимо объявить <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> событий и создать `OnPropertyChanged` метод. Затем для каждого свойства, которому потребуются уведомления об изменениях, вы вызываете `OnPropertyChanged` при каждом обновлении свойства.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Пример того, как `Person` класс может использоваться для поддержки <xref:System.Windows.Data.BindingMode.TwoWay> привязки, в разделе [управления, если текст в текстовом поле обновляет источник](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
