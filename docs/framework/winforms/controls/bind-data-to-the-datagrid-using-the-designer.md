---
title: Привязка данных к элементу управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: d5fab6acc53e5b8be247e958bdba78f0d3647fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744113"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора
Конструктор можно использовать для подключения элемента управления <xref:System.Windows.Forms.DataGridView> к источникам данных нескольких различных видов, включая базы данных, бизнес-объекты или веб-службы. При привязке элемента управления к источнику данных с помощью конструктора элемент управления автоматически привязывается к <xref:System.Windows.Forms.BindingSource> компоненту, представляющему источник данных. Кроме того, в элементе управления автоматически создаются столбцы для сопоставления данных о схеме, предоставляемых источником данных.

 После этого созданные столбцы можно будет изменить с учетом ваших потребностей. Например, можно удалить или скрыть столбцы, которые вас не интересуют, изменить порядок или типы столбцов. Дополнительные сведения об изменении столбцов см. в разделах, перечисленных в разделе "См. также".

 Можно также привязать несколько элементов управления <xref:System.Windows.Forms.DataGridView> к связанным таблицам для создания связей "основной/подробности". В данной конфигурации один элемент управления отображает родительскую таблицу, а другой — только те строки из дочерней таблицы, которые связаны с текущей строкой в родительской таблице. Дополнительные сведения см. в разделе [Практическое руководство. Отображение связанных данные в приложении Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView> или два элемента управления для отношения "основной/подробности". Сведения о запуске такого проекта см. в разделе [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-bind-the-control-to-a-data-source"></a>Привязка элемента управления к источнику данных

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>.

2. Щелкните стрелку раскрывающегося списка рядом с параметром **Выбор источника данных**.

3. Если у проекта еще нет источника данных, нажмите **Добавить источник данных проекта** и следуйте указаниям мастера.

     Дополнительные сведения см. в разделе [Мастер настройки источника данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120)). Новый источник данных появится в раскрывающемся окне **Выбор источника данных**. Если источник данных содержит только один элемент, например только одну таблицу баз данных, элемент управления будет автоматически привязан к этому элементу. В противном случае перейдите к следующему этапу.

4. Разверните узлы **Другие источники данных** и **Источники данных проекта**, если они еще не развернуты, и выберите источник данных, к которому нужно привязать элемент управления.

5. Если источник данных содержит более одного элемента, например, если создан <xref:System.Data.DataSet?displayProperty=nameWithType>, содержащий несколько таблиц, разверните источник данных, а затем выберите конкретный элемент для привязки.

6. Чтобы создать отношение "основной/подробности", в раскрывающемся окне **Выбор источника данных** для второго элемента управления <xref:System.Windows.Forms.DataGridView> разверните <xref:System.Windows.Forms.BindingSource>, созданную для родительской таблицы, а затем выберите связанную дочернюю таблицу из отображаемого списка.

    > [!NOTE]
    > Если в вашем проекте уже есть источник данных, форму данных можно также создать в окне **Источники данных**. Дополнительные сведения см. в разделе [Окно источников данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120)).

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Практическое руководство. Подключение к данным в базе данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](hide-columns-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Окно "источники данных"](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [Практическое руководство. Отображение связанных данные в приложении Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))
