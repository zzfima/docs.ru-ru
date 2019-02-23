---
title: Привязка данных Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: b33ad9d78230588b9c1afd5d59fd0333e2cd18a6
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747065"
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
  
 [Практическое руководство. Переход между данными в Windows Forms](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 Показано, как перемещаться по элементам в источнике данных.  
  
 [Уведомления об изменениях в привязке данных Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 Описывает различные типы уведомлений об изменении для привязки данных Windows Forms.  
  
 [Практическое руководство. Реализация интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>. Этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта  
  
 [Практическое руководство. Применение шаблона PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 Демонстрирует применение *PropertyName*шаблон Changed к свойствам пользовательского элемента управления Windows Forms.  
  
 [Практическое руководство. Реализация интерфейса ITypedList](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 Показано, как задействовать обнаружение схемы для связываемого списка путем реализации интерфейса <xref:System.ComponentModel.ITypedList>.  
  
 [Практическое руководство. Реализация интерфейса IListSource](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 Показано, как реализовать интерфейс <xref:System.ComponentModel.IListSource>, чтобы создать связываемый класс, который не реализует <xref:System.Collections.IList>, но предоставляет список из другого расположения.  
  
 [Практическое руководство. Элементов управления с привязкой к тому же источнику данных будут синхронизированы](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 Показано, как обрабатывать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для обеспечения синхронизация всех элементов управления, привязанных к источнику данных.  
  
 [Практическое руководство. Убедитесь, что выбранной строки в дочерней таблице остается в правильном положении](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 Показано, как обеспечить сохранение позиции выбранной строки дочерней таблицы при изменении поля родительской таблицы.  
  
 Также см. в разделе [интерфейсы, относящиеся к привязке данных](interfaces-related-to-data-binding.md), [как: Переход между данными в Windows Forms](how-to-navigate-data-in-windows-forms.md), и [как: Создание элемента управления простой привязкой в форме Windows](how-to-create-a-simple-bound-control-on-a-windows-form.md).  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 Описывает класс, представляющий связку между связываемым компонентом и источником данных.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 Описывает класс, инкапсулирующий источник данных для привязки к элементам управления.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компонент BindingSource](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 Содержит список разделов, описывающих использование компонента <xref:System.Windows.Forms.BindingSource>.  
  
 [Элемент управления DataGridView](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 Предоставляет список разделов, в которых демонстрируется использование связываемого элемента управления datagrid.  
  
 Также см. в разделе [доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).
