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
ms.openlocfilehash: 4f9ff49a443577e119b0c1079abbe23bd7ede4c4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459746"
---
# <a name="how-to-implement-property-change-notification"></a>Практическое руководство. Реализация уведомления об изменении свойства
Чтобы обеспечить поддержку привязки <xref:System.Windows.Data.BindingMode.OneWay> или <xref:System.Windows.Data.BindingMode.TwoWay>, чтобы свойства целевого объекта привязки автоматически отражали динамические изменения источника привязки (например, для автоматического обновления области просмотра при редактировании пользователем формы), классу необходимо укажите правильные уведомления об изменении свойств. В этом примере показано, как создать класс, реализующий <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## <a name="example"></a>Пример  
 Для реализации <xref:System.ComponentModel.INotifyPropertyChanged> необходимо объявить событие <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> и создать метод `OnPropertyChanged`. Затем для каждого свойства, которому потребуются уведомления об изменениях, вы вызываете `OnPropertyChanged` при каждом обновлении свойства.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Пример того, как можно использовать класс `Person` для поддержки привязки <xref:System.Windows.Data.BindingMode.TwoWay>, см. в разделе [Управление обновлением источника в текстовом поле](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения об источниках привязки](binding-sources-overview.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
