---
title: Привязка данных
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: 68871db848ab46b88865e668f27f09972e8debcf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734608"
---
# <a name="windows-forms-data-binding"></a>Привязка данных Windows Forms
Привязка данных в Windows Forms дает возможность отображать и изменять информацию из источника данных в элементах управления в форме. В Windows Forms можно выполнить привязку не только к традиционным источникам данных, но и к практически к любой структуре, содержащий данные.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Привязка данных и Windows Forms](data-binding-and-windows-forms.md)  
 Общие сведения о привязке данных в Windows Forms.  
  
 [Источники данных, поддерживаемые Windows Forms](data-sources-supported-by-windows-forms.md)  
 Описывает источники данных, которые можно использовать с Windows Forms.  
  
 [Интерфейсы, относящиеся к привязке данных](interfaces-related-to-data-binding.md)  
 Описывает некоторые интерфейсы, используемые для привязки данных Windows Forms.  
  
 [Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms](how-to-navigate-data-in-windows-forms.md)  
 Показано, как перемещаться по элементам в источнике данных.  
  
 [Уведомления об изменениях в привязке данных Windows Forms](change-notification-in-windows-forms-data-binding.md)  
 Описывает различные типы уведомлений об изменении для привязки данных Windows Forms.  
  
 [Практическое руководство. Реализация интерфейса INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>. Этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта  
  
 [Практическое руководство. Применение шаблона PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)  
 Показывает, как применить шаблон " *PropertyName*Changed" к свойствам Windows Forms пользовательского элемента управления.  
  
 [Практическое руководство. Реализация интерфейса ITypedList](how-to-implement-the-itypedlist-interface.md)  
 Показано, как задействовать обнаружение схемы для связываемого списка путем реализации интерфейса <xref:System.ComponentModel.ITypedList>.  
  
 [Практическое руководство. Реализация интерфейса IListSource](how-to-implement-the-ilistsource-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.IListSource>, чтобы создать связываемый класс, который не реализует <xref:System.Collections.IList>, но предоставляет список из другого расположения.  
  
 [Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных](multiple-controls-bound-to-data-source-synchronized.md)  
 Показано, как обрабатывать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для обеспечения синхронизация всех элементов управления, привязанных к источнику данных.  
  
 [Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице](ensure-the-selected-row-in-a-child-table-correct.md)  
 Показано, как обеспечить сохранение позиции выбранной строки дочерней таблицы при изменении поля родительской таблицы.  
  
 См. также [интерфейсы, связанные с привязкой данных](interfaces-related-to-data-binding.md), [как перемещать данные в Windows Forms](how-to-navigate-data-in-windows-forms.md)и [как создавать элементы управления с простой привязкой в форме Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md).  
  
## <a name="reference"></a>Справочник  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 Описывает класс, представляющий связку между связываемым компонентом и источником данных.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 Описывает класс, инкапсулирующий источник данных для привязки к элементам управления.  
  
## <a name="related-sections"></a>См. также  
 [Компонент BindingSource](./controls/bindingsource-component.md)  
 Содержит список разделов, описывающих использование компонента <xref:System.Windows.Forms.BindingSource>.  
  
 [Элемент управления DataGridView](./controls/datagridview-control-windows-forms.md)  
 Предоставляет список разделов, в которых демонстрируется использование связываемого элемента управления datagrid.  
  
 Также см. раздел [доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).
