---
title: Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: d1e598831954f17bdf3bc03ab880c344ca36aa5a
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039943"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора

> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

 Если содержит ряд связанных таблиц, можно использовать два <xref:System.Windows.Forms.DataGrid> элемента управления для отображения данных в формате «основной/подробности». <xref:System.Data.DataSet> Один <xref:System.Windows.Forms.DataGrid> из них обозначен как Главная сетка, а второй — сеткой сведений. При выборе записи в главном списке все связанные дочерние записи отображаются в списке подробностей. Например, если <xref:System.Data.DataSet> содержит таблицу Customers и связанную таблицу Orders, можно указать таблицу Customers, которая будет главной сеткой, а таблица Orders — сетку сведений. При выборе клиента из главной сетки все заказы, связанные с этим клиентом в таблице Orders, будут отображаться в сетке сведений.

 Для следующей процедуры требуется проект **приложения Windows** (**файл** > **создать** > **проект** > **визуальный C#**  элемент или **Visual Basic**  >   **Классическое** **Windows Forms приложение**). > 

## <a name="to-create-a-master-details-list-in-the-designer"></a>Создание списка «основной/подробности» в конструкторе

1. Добавьте в <xref:System.Windows.Forms.DataGrid> форму два элемента управления. Дополнительные сведения см. в разделе [Практическое руководство. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms. В Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> элемент управления не находится на **панели элементов** по умолчанию. Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов на панель элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

    > [!NOTE]
    >  Следующие шаги неприменимы к Visual Studio 2005, в котором для привязки данных времени разработки используется окно **Источники данных** . Дополнительные сведения см. в статьях [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) и [выполнение следующих действий. Отображение связанных данных в приложении](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))Windows Forms.

2. Перетащите несколько таблиц из **Обозреватель сервера** в форму.

3. В меню **данные** выберите **создать набор данных**.

4. Установите связи между таблицами с помощью конструктора XML. Дополнительные сведения см. в разделе «как Создание связей "один ко многим" в XML-схемах и наборах данных "на сайте MSDN.

5. Сохраните связи, выбрав **сохранить все** в меню **файл** .

6. <xref:System.Windows.Forms.DataGrid> Настройте элемент управления, который необходимо назначить главной сеткой, следующим образом.

    1. Выберите из раскрывающегося списка <xref:System.Windows.Forms.DataGrid.DataSource%2A> в свойстве. <xref:System.Data.DataSet>

    2. Выберите главную таблицу (например, "Customers") в раскрывающемся списке <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойства.

7. <xref:System.Windows.Forms.DataGrid> Настройте элемент управления, который требуется назначить сетку сведений, следующим образом:

    1. Выберите из раскрывающегося списка <xref:System.Windows.Forms.DataGrid.DataSource%2A> в свойстве. <xref:System.Data.DataSet>

    2. Выберите связь (например, "Customers. кусторд") между главной таблицей и таблицами сведений в <xref:System.Windows.Forms.DataGrid.DataMember%2A> раскрывающемся списке свойства. Чтобы увидеть связь, разверните узел, щелкнув знак "плюс" ( **+** ) рядом с главной таблицей в раскрывающемся списке.

## <a name="see-also"></a>См. также

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Привязка Windows Forms элемента управления DataGrid к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
