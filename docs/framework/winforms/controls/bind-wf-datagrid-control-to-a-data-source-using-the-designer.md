---
title: Привязка элемента управления DataGrid к источнику данных с помощью конструктора
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: cc0a74eca40e34f06b065980d25d922b919b0c3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744086"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

 Элемент управления Windows Forms <xref:System.Windows.Forms.DataGrid> специально разработан для вывода информации из источника данных. Элемент управления привязывается во время разработки путем задания свойств <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> или во время выполнения путем вызова метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>. Несмотря на то, что можно отображать данные из различных источников данных, наиболее типичными источниками являются наборы данных и представления.

 Если источник данных доступен во время разработки, например, если форма содержит экземпляр набора данных или представление данных, можно привязать сетку к источнику данных во время разработки. Затем можно просмотреть, как будут выглядеть данные в сетке.

 Можно также выполнить привязку сетки программным способом во время выполнения. Это полезно, если необходимо задать источник данных на основе сведений, получаемых во время выполнения. Например, приложение может позволить пользователю указать имя таблицы для просмотра. Это также необходимо в ситуациях, когда источник данных не существует во время разработки. К ним относятся такие источники данных, как массивы, коллекции, нетипизированные DataSet и модули чтения данных.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGrid>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md). В Visual Studio 2005 элемент управления <xref:System.Windows.Forms.DataGrid> по умолчанию не находится на **панели элементов** . Дополнительные сведения о добавлении элементов см. в разделе [как добавить элементы на панель элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)). Кроме того, в Visual Studio 2005 можно использовать окно **Источники данных** для привязки данных во время разработки. Дополнительные сведения см. [в разделе Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Привязка данных элемента управления DataGrid к одной таблице в конструкторе

1. Задайте для свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> элемента управления объект, содержащий элементы данных, к которым необходимо выполнить привязку.

2. Если источник данных является набором данных, задайте для свойства <xref:System.Windows.Forms.DataGrid.DataMember%2A> имя таблицы, к которой выполняется привязка.

3. Если источник данных является набором данных или представлением данных, основанным на таблице набора данных, добавьте в форму код для заполнения набора данных.

     Точный код, который вы используете, зависит от того, где набор данных получает данные. Если набор данных заполняется непосредственно из базы данных, обычно вызывается метод `Fill` адаптера данных, как показано в следующем примере кода, который заполняет набор данных с именем `DsCategories1`:

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. Используемых Добавьте соответствующие стили таблиц и столбцов в сетку.

     Если стили таблиц отсутствуют, вы увидите таблицу, но с минимальным форматированием и отображением всех столбцов.

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Привязка элемента управления DataGrid к нескольким таблицам в наборе данных в конструкторе

1. Задайте для свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> элемента управления объект, содержащий элементы данных, к которым необходимо выполнить привязку.

2. Если набор данных содержит связанные таблицы (то есть, если он содержит объект связи), задайте для свойства <xref:System.Windows.Forms.DataGrid.DataMember%2A> имя родительской таблицы.

3. Напишите код для заполнения набора данных.

## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
- [Доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
