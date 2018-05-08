---
title: Практическое руководство. Реализация интерфейса INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 8f64b51a7d56f609399baac613a651e82b91e6df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Практическое руководство. Реализация интерфейса INotifyPropertyChanged
В следующем примере кода показано, как реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейса. Реализуйте этот интерфейс бизнес-объекты, которые используются в процессе привязки данных Windows Forms. При реализации этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Применение шаблона PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 [Привязка данных Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 [Уведомления об изменениях в привязке данных Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
