---
title: Создание списков «основной/подробности» с помощью элемента управления DataGrid в конструкторе
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 0dea3dd88a8c6c2aceb894789ace8ef3b5c83632
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743384"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

 Если <xref:System.Data.DataSet> содержит ряд связанных таблиц, можно использовать два элемента управления <xref:System.Windows.Forms.DataGrid> для отображения данных в формате "основной/подробности". Один <xref:System.Windows.Forms.DataGrid> обозначен как Главная сетка, а второй — сеткой сведений. При выборе записи в главном списке все связанные дочерние записи отображаются в списке подробностей. Например, если <xref:System.Data.DataSet> содержит таблицу Customers и связанную таблицу Orders, то необходимо указать таблицу Customers, которая будет главной сеткой, а таблица Orders — сетку сведений. При выборе клиента из главной сетки все заказы, связанные с этим клиентом в таблице Orders, будут отображаться в сетке сведений.

 Для следующей процедуры требуется проект **приложения Windows** (**файл** > **Новый** > **проект** > **Visual C#**  или **Visual Basic** > **классический рабочий стол** > **Windows Forms приложения**).

## <a name="to-create-a-master-details-list-in-the-designer"></a>Создание списка «основной/подробности» в конструкторе

1. Добавьте в форму два элемента управления <xref:System.Windows.Forms.DataGrid>. Дополнительные сведения см. [в разделе руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md). В Visual Studio 2005 элемент управления <xref:System.Windows.Forms.DataGrid> по умолчанию не находится на **панели элементов** . Дополнительные сведения см. в разделе [как добавить элементы на панель элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

    > [!NOTE]
    > Следующие шаги неприменимы к Visual Studio 2005, в котором для привязки данных времени разработки используется окно **Источники данных** . Дополнительные сведения см. в статьях [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) и [инструкции. Отображение связанных данных в Windows Forms приложении](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).

2. Перетащите несколько таблиц из **Обозреватель сервера** в форму.

3. В меню **данные** выберите **создать набор данных**.

4. Установите связи между таблицами с помощью конструктора XML. Дополнительные сведения см. в разделе "инструкции. Создание связей" один ко многим "в XML-схемах и наборах данных" на сайте MSDN.

5. Сохраните связи, выбрав **сохранить все** в меню **файл** .

6. Настройте элемент управления <xref:System.Windows.Forms.DataGrid>, который нужно назначить главной сеткой, следующим образом.

    1. Выберите <xref:System.Data.DataSet> из раскрывающегося списка в свойстве <xref:System.Windows.Forms.DataGrid.DataSource%2A>.

    2. Выберите главную таблицу (например, "Customers") из раскрывающегося списка в свойстве <xref:System.Windows.Forms.DataGrid.DataMember%2A>.

7. Настройте элемент управления <xref:System.Windows.Forms.DataGrid>, который требуется назначить сетку сведений, следующим образом.

    1. Выберите <xref:System.Data.DataSet> из раскрывающегося списка в свойстве <xref:System.Windows.Forms.DataGrid.DataSource%2A>.

    2. Выберите связь (например, "Customers. Кусторд") между главной таблицей и таблицами сведений из раскрывающегося списка в свойстве <xref:System.Windows.Forms.DataGrid.DataMember%2A>. Чтобы увидеть связь, разверните узел, щелкнув знак плюса ( **+** ) рядом с главной таблицей в раскрывающемся списке.

## <a name="see-also"></a>См. также:

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
