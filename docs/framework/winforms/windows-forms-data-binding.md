---
title: "Связывание элементов управления Windows Forms с данными | Microsoft Docs"
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
  - "элементы управления с привязкой, Windows Forms"
  - "данные [Windows Forms]"
  - "данные [Windows Forms], архитектура"
  - "Элементы управления Windows Forms, привязка данных"
  - "Windows Forms, привязка данных"
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Связывание элементов управления Windows Forms с данными
Привязка данных в Windows Forms дает возможность отображать и изменять информацию из источника данных в элементах управления в форме.  В Windows Forms можно выполнить привязку не только к традиционным источникам данных, но и к практически к любой структуре, содержащий данные.  
  
## В этом подразделе  
 [Связывание данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 Общие сведения о привязке данных в Windows Forms.  
  
 [Источники данных, поддерживаемые Windows Forms](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 Описывает источники данных, которые можно использовать с Windows Forms.  
  
 [Интерфейсы, относящиеся к связыванию данных](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 Описывает некоторые интерфейсы, используемые для привязки данных Windows Forms.  
  
 [Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 Показано, как перемещаться по элементам в источнике данных.  
  
 [Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 Описывает различные типы уведомлений об изменении для привязки данных Windows Forms.  
  
 [Практическое руководство. Реализация интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>.  Этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес\-объекта  
  
 [Практическое руководство. Применение шаблона PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 Показано, как применить шаблон *PropertyName*Changed к свойствам пользовательского элемента управления Windows Forms.  
  
 [Практическое руководство. Реализация интерфейса ITypedList](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 Показано, как задействовать обнаружение схемы для связываемого списка путем реализации интерфейса <xref:System.ComponentModel.ITypedList>.  
  
 [Практическое руководство. Реализация интерфейса IListSource](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.IListSource>, чтобы создать связываемый класс, который не реализует <xref:System.Collections.IList>, но предоставляет список из другого расположения.  
  
 [Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 Показано, как обрабатывать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для обеспечения синхронизация всех элементов управления, привязанных к источнику данных.  
  
 [Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 Показано, как обеспечить сохранение позиции выбранной строки дочерней таблицы при изменении поля родительской таблицы.  
  
 См. также [Интерфейсы, которые относятся к привязке данных](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).  
  
## Ссылка  
 <xref:System.Windows.Forms.Binding?displayProperty=fullName>  
 Описывает класс, представляющий связку между связываемым компонентом и источником данных.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=fullName>  
 Описывает класс, инкапсулирующий источник данных для привязки к элементам управления.  
  
## Связанные подразделы  
 [Компонент BindingSource](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 Содержит список разделов, описывающих использование компонента <xref:System.Windows.Forms.BindingSource>.  
  
 [Элемент управления DataGridView](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 Предоставляет список разделов, в которых демонстрируется использование связываемого элемента управления datagrid.  
  
 См. также [Доступ к данным в Visual Studio](http://msdn.microsoft.com/library/wzabh8c4\(v=vs.110\)) или [Доступ к данным в Visual Studio](http://msdn.microsoft.com/library/wzabh8c4\(v=vs.110\)).