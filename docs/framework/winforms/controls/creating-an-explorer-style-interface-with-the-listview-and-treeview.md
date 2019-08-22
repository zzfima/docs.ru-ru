---
title: Пошаговое руководство. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: d80f8e3bc729689b274af520bc37fda8417b0407
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658573"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Пошаговое руководство. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора

Одним из преимуществ Visual Studio является возможность создания профессионально оформленных Windows Forms приложений в течение короткого промежутка времени. Распространенным сценарием является создание пользовательского интерфейса с <xref:System.Windows.Forms.ListView> элементами управления и <xref:System.Windows.Forms.TreeView> , которые похожи на проводник Windows в операционных системах Windows. Проводник Windows отображает иерархическую структуру файлов и папок на компьютере пользователя.

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Создание формы, содержащей элемент управления ListView и TreeView

1. В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.

2. В диалоговом окне **Новый проект** выполните следующие действия.

    1. В категории выберите либо **Visual Basic** , либо **визуальный C#** элемент.

    2. В списке шаблонов выберите **Windows Forms приложение**.

3. Нажмите кнопку **ОК**. Будет создан новый проект Windows Forms.

4. Добавьте в форму <xref:System.Windows.Forms.SplitContainer.Dock%2A> <xref:System.Windows.Forms.DockStyle.Fill>элемент управления и задайте для его свойства значение. <xref:System.Windows.Forms.SplitContainer>

5. Добавьте именованный `imageList1` элемент в форму и используйте окно свойств, чтобы добавить два изображения: изображение папки и изображение документа в указанном порядке. <xref:System.Windows.Forms.ImageList>

6. Добавьте элемент управления с `treeview1` именем в форму и разместите его в левой <xref:System.Windows.Forms.SplitContainer> части элемента управления. <xref:System.Windows.Forms.TreeView> В окно свойств `treeView1` выполните следующие действия.

    1. Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Задайте свойству <xref:System.Windows.Forms.TreeView.ImageList%2A> значение `imagelist1.`

7. Добавьте элемент управления с `listView1` именем в форму и разместите его в правой <xref:System.Windows.Forms.SplitContainer> части элемента управления. <xref:System.Windows.Forms.ListView> В окно свойств `listview1` выполните следующие действия.

    1. Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Задайте для свойства <xref:System.Windows.Forms.ListView.View%2A> значение <xref:System.Windows.Forms.View.Details>.

    3. Откройте редактор коллекции колумнхеадер, нажав кнопку с многоточием (![...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) в <xref:System.Windows.Forms.ListView.Columns%2A> свойстве **.** Добавьте три столбца и задайте для <xref:System.Windows.Forms.ColumnHeader.Text%2A> `Name`них свойства, `Type`и `Last Modified`соответственно. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.

    4. Задайте свойству <xref:System.Windows.Forms.ListView.SmallImageList%2A> значение `imageList1.`

8. Реализуйте код, чтобы заполнить <xref:System.Windows.Forms.TreeView> узлы и подузлы. Добавьте этот код в `Form1` класс.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. Поскольку в предыдущем коде используется пространство имен System.IO, добавьте соответствующий оператор using или Import в верхней части формы.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. Вызовите метод Set-up из предыдущего шага в конструкторе формы или <xref:System.Windows.Forms.Form.Load> методе обработки событий. Добавьте этот код в конструктор формы.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. Обработайте `treeview1` событиедля`listview1` и реализуйте код, который заполняется содержимым узла при щелчке узла. <xref:System.Windows.Forms.TreeView.NodeMouseClick> Добавьте этот код в `Form1` класс.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     Если используется C#, убедитесь, что у вас есть <xref:System.Windows.Forms.TreeView.NodeMouseClick> событие, связанное с методом обработки событий. Добавьте этот код в конструктор формы.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Нажмите клавишу F5 для запуска приложения.

     Вы увидите разделенную форму, содержащую <xref:System.Windows.Forms.TreeView> элемент управления, который отображает каталог проекта слева, <xref:System.Windows.Forms.ListView> и элемент управления с правой стороны с тремя столбцами. Можно просмотреть <xref:System.Windows.Forms.TreeView> , выбрав узлы каталога, <xref:System.Windows.Forms.ListView> и заполнится содержимым выбранного каталога.

## <a name="next-steps"></a>Следующие шаги

Это приложение предоставляет пример того, как можно использовать <xref:System.Windows.Forms.TreeView> вместе элементы управления и. <xref:System.Windows.Forms.ListView> Дополнительные сведения об этих элементах управления см. в следующих разделах:

- [Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [Практическое руководство. Добавление возможностей поиска в элемент управления ListView](how-to-add-search-capabilities-to-a-listview-control.md)

- [Практическое руководство. Присоединение контекстного меню к узлу TreeView](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Практическое руководство. Добавление и удаление узлов с помощью элемента управления Windows Forms TreeView](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление столбцов в Windows Forms элемент управления ListView](how-to-add-columns-to-the-windows-forms-listview-control.md)
