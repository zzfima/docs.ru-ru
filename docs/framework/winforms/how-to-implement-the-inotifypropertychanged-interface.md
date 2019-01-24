---
title: Как выполнить Реализация интерфейса INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: c92406899cffa56a1001f50f89cb53303df5da39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560078"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Как выполнить Реализация интерфейса INotifyPropertyChanged
В следующем примере кода показано, как реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс. Реализуйте этот интерфейс для бизнес-объектов, которые используются в привязке данных Windows Forms. При реализации, этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Применение шаблона PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)
- [Привязка данных Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
- [Практическое руководство. Получение уведомления об изменении с помощью компонента BindingSource и интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)
- [Уведомления об изменениях в привязке данных Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
