---
title: Практическое руководство. Реализация интерфейса INotifyPropertyChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: cfdfb22fd854a8f630243e0f612761c71cb778d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225603"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Практическое руководство. Реализация интерфейса INotifyPropertyChanged
В следующем примере кода показано, как реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс. Реализуйте этот интерфейс для бизнес-объектов, которые используются в привязке данных Windows Forms. При реализации, этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Применение шаблона PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
- [Практическое руководство. Получение уведомления об изменении с помощью компонента BindingSource и интерфейса INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md)
- [Уведомления об изменениях в привязке данных Windows Forms](change-notification-in-windows-forms-data-binding.md)
