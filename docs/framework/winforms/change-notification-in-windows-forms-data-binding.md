---
title: "Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, добавление уведомления об изменении к привязке данных"
  - "Windows Forms, привязка данных"
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms
Одним из наиболее важных понятий привязки данных Windows Forms является *уведомление об изменении*.  Для того чтобы источник данных и связанные элементы управления содержали самые последние данные, необходимо добавить к привязке данных уведомление об изменении.  Иными словами, требуется уведомлять связанные элементы управления об изменениях, выполненных в источнике данных, а источник данных — об изменениях связанных свойств элементов управления.  
  
 В зависимости от вида привязки данных, существуют различные виды уведомлений об изменении.  
  
-   Простая привязка, при которой одно свойство элемента управления привязывается к одному экземпляру объекта.  
  
-   Привязка на основе списка, которая позволяет привязывать одно свойство элемента управления к свойству элемента списка или свойство элемента управления к списку объектов.  
  
 Кроме того, при создании элементов управления Windows Forms, которые необходимо использовать для привязки данных, требуется применить к этим элемента управления шаблон *PropertyName*Changed, чтобы изменения связанных свойств элемента управления отражались в источнике данных.  
  
## Уведомление об изменении для простой привязки  
 В случае простой привязки бизнес\-объекты должны отправлять уведомления об изменении при изменении значения связанного свойства.  Для этого можно предоставить событие *PropertyName*Changed для каждого свойства бизнес\-объекта и привязать бизнес\-объект к элементам управления с помощью компонента <xref:System.Windows.Forms.BindingSource> или использовать рекомендуемый метод, который заключается в том, что бизнес\-объект реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> и инициирует событие <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> при изменении значения свойства.  Дополнительные сведения см. в разделе [Практическое руководство. Реализация интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md).  Если бизнес\-объект реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>, использование компонента <xref:System.Windows.Forms.BindingSource> для привязки объекта к элементу управления становится необязательным, однако рекомендуется все же использовать компонент <xref:System.Windows.Forms.BindingSource>.  
  
## Уведомление об изменении для привязки на основе списка  
 Для предоставления связанным элементам управления сведений об изменении свойства \(т.е. изменении значения свойства элемента списка\) или списка \(т.е. об удалении или добавлении элемента списка\) Windows Forms опирается на связанный список.  Поэтому списки, используемые для привязки данных, должны реализовывать интерфейс <xref:System.ComponentModel.IBindingList>, который поддерживает оба типа уведомлений об изменении.  Класс <xref:System.ComponentModel.BindingList%601>, который представляет собой общую реализацию интерфейса <xref:System.ComponentModel.IBindingList>, предназначен для использования вместе с привязкой данных Windows Forms.  Можно создать класс <xref:System.ComponentModel.BindingList%601>, содержащий тип бизнес\-объекта, который реализует интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>, после чего список будет автоматически преобразовывать события <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> в события <xref:System.ComponentModel.IBindingList.ListChanged>.  Если связанный список не реализует интерфейс <xref:System.ComponentModel.IBindingList>, необходимо привязать список объектов к элементам управления Windows Forms с помощью компонента <xref:System.Windows.Forms.BindingSource>.  Компонент <xref:System.Windows.Forms.BindingSource> обеспечивает преобразование свойства в список, аналогичное операции, выполняемой классом <xref:System.ComponentModel.BindingList%601>.  Дополнительные сведения см. в разделе [Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).  
  
## Уведомление об изменении для пользовательских элементов управления  
 И наконец, на стороне элементов управления можно предоставить событие *PropertyName*Changed для каждого свойства, предназначенного для привязки данных.  После этого изменения свойств элемента управления будут отражаться в связанном источнике данных.  Дополнительные сведения см. в разделе [Практическое руководство. Применение шаблона PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md).  
  
## См. также  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.ComponentModel.INotifyPropertyChanged>   
 <xref:System.ComponentModel.BindingList%601>   
 [Связывание элементов управления Windows Forms с данными](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Источники данных, поддерживаемые Windows Forms](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [Связывание данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)