---
title: "Привязка данных Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77f01bc462be67c3b613b8ab102a359a80d74140
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-data-binding"></a>Привязка данных Windows Forms
Привязка данных в Windows Forms дает возможность отображать и изменять информацию из источника данных в элементах управления в форме. В Windows Forms можно выполнить привязку не только к традиционным источникам данных, но и к практически к любой структуре, содержащий данные.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Привязка данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 Общие сведения о привязке данных в Windows Forms.  
  
 [Источники данных, поддерживаемые Windows Forms](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 Описывает источники данных, которые можно использовать с Windows Forms.  
  
 [Интерфейсы, относящиеся к привязке данных](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 Описывает некоторые интерфейсы, используемые для привязки данных Windows Forms.  
  
 [Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 Показано, как перемещаться по элементам в источнике данных.  
  
 [Уведомления об изменениях в привязке данных Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 Описывает различные типы уведомлений об изменении для привязки данных Windows Forms.  
  
 [Практическое руководство. Реализация интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>. Этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта  
  
 [Практическое руководство. Применение шаблона PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 Показано, как применить *PropertyName*шаблон Changed к свойствам пользовательского элемента управления Windows Forms.  
  
 [Практическое руководство. Реализация интерфейса ITypedList](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 Показано, как задействовать обнаружение схемы для связываемого списка путем реализации интерфейса <xref:System.ComponentModel.ITypedList>.  
  
 [Практическое руководство. Реализация интерфейса IListSource](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.IListSource>, чтобы создать связываемый класс, который не реализует <xref:System.Collections.IList>, но предоставляет список из другого расположения.  
  
 [Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 Показано, как обрабатывать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для обеспечения синхронизация всех элементов управления, привязанных к источнику данных.  
  
 [Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 Показано, как обеспечить сохранение позиции выбранной строки дочерней таблицы при изменении поля родительской таблицы.  
  
 См. также [интерфейсы, связанные с привязкой данных](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [как: перемещения данных в Windows Forms](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [как: Создание элемента управления простой привязкой в форме Windows](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\)).  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 Описывает класс, представляющий привязку связываемых компонентов к источнику данных.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 Описывает класс, инкапсулирующий источник данных для привязки к элементам управления.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компонент BindingSource](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 Содержит список разделов, описывающих использование компонента <xref:System.Windows.Forms.BindingSource>.  
  
 [Элемент управления DataGridView](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 Предоставляет список разделов, в которых демонстрируется использование связываемого элемента управления datagrid.  
  
 См. также [доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).
