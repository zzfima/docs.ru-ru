---
title: Уведомление об изменении в привязке данных
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 2dffea46bf0db54d28ef55e507767d88bd29ebc2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746346"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms
Одним из наиболее важных концепций привязки данных Windows Forms является *уведомление об изменениях*. Чтобы гарантировать, что источник данных и привязанные элементы управления всегда будут иметь самые последние данные, необходимо добавить уведомление об изменении для привязки данных. В частности, необходимо убедиться, что привязанные элементы управления получают уведомления об изменениях, внесенных в источник данных, а источник данных уведомляет об изменениях, внесенных в связанные свойства элемента управления.  
  
 Существуют различные виды уведомлений об изменениях в зависимости от типа привязки данных.  
  
- Простая привязка, в которой одно свойство элемента управления привязано к одному экземпляру объекта.  
  
- Привязка на основе списка, которая может включать одно свойство элемента управления, привязанное к свойству элемента в списке, или свойство элемента управления, привязанное к списку объектов.  
  
 Кроме того, при создании Windows Forms элементов управления, которые будут использоваться для привязки данных, необходимо применить шаблон " *PropertyName*Changed" к элементам управления, чтобы изменения привязанного свойства элемента управления распространялись на источник данных.  
  
## <a name="change-notification-for-simple-binding"></a>Уведомление об изменении для простой привязки  
 Для простой привязки бизнес-объекты должны предоставлять уведомление об изменении при изменении значения привязанного свойства. Это можно сделать, предоставив событие *PropertyName*Changed для каждого свойства бизнес-объекта и привязывая бизнес-объект к элементам управления с помощью <xref:System.Windows.Forms.BindingSource> или предпочтительного метода, в котором ваш бизнес-объект реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>, и вызывает событие <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> при изменении значения свойства. Дополнительные сведения см. в разделе [инструкции. Реализация интерфейса INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md). При использовании объектов, реализующих интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>, не нужно использовать <xref:System.Windows.Forms.BindingSource> для привязки объекта к элементу управления, но рекомендуется использовать <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="change-notification-for-list-based-binding"></a>Уведомление об изменении для привязки на основе списка  
 Windows Forms зависит от связанного списка для предоставления изменения свойства (изменения значения свойства элемента списка) и измененного списка (элемент удаляется или добавляется в список) в привязанные элементы управления. Таким образом, списки, используемые для привязки данных, должны реализовывать <xref:System.ComponentModel.IBindingList>, который предоставляет оба типа уведомлений об изменениях. <xref:System.ComponentModel.BindingList%601> является универсальной реализацией <xref:System.ComponentModel.IBindingList> и предназначена для использования с Windows Forms привязкой данных. Можно создать <xref:System.ComponentModel.BindingList%601>, содержащий тип бизнес-объекта, который реализует <xref:System.ComponentModel.INotifyPropertyChanged>, и список автоматически преобразует события <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> в <xref:System.ComponentModel.IBindingList.ListChanged> события. Если связанный список не является <xref:System.ComponentModel.IBindingList>, необходимо привязать список объектов к Windows Forms элементам управления с помощью компонента <xref:System.Windows.Forms.BindingSource>. Компонент <xref:System.Windows.Forms.BindingSource> предоставит преобразование свойства в список, аналогичное <xref:System.ComponentModel.BindingList%601>. Дополнительные сведения см. [в разделе как создавать уведомления об изменениях с помощью BindingSource и интерфейса INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Уведомление об изменении пользовательских элементов управления  
 Наконец, на стороне элемента управления необходимо предоставить событие *PropertyName*Changed для каждого свойства, предназначенного для привязки к данным. Изменения свойства элемента управления передаются в связанный источник данных. Дополнительные сведения см. в разделе [как применить шаблон PropertyNameChanged.](how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
- [Источники данных, поддерживаемые Windows Forms](data-sources-supported-by-windows-forms.md)
- [Привязка данных и Windows Forms](data-binding-and-windows-forms.md)
