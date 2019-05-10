---
title: Пошаговое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211562"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Пошаговое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip

Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> поддерживает приложения с интерфейсом MDI, а элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает слияние меню. Формы MDI также могут содержать элементы управления <xref:System.Windows.Forms.ToolStrip>.

В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.ToolStripPanel> элементов управления с формой MDI. Форма также поддерживает слияние меню с вложенными меню. В этом пошаговом руководстве показаны следующие задачи:

- Создание проекта Windows Forms.

- Создание главного меню для формы. Фактическое имя меню будет отличаться.

- Добавление <xref:System.Windows.Forms.ToolStripPanel> управления **элементов**.

- Создание дочерней формы.

- Упорядочение <xref:System.Windows.Forms.ToolStripPanel> элементов управления по оси z.

Когда вы закончите, вы получите формы MDI, которая поддерживает слияние меню и movable <xref:System.Windows.Forms.ToolStrip> элементов управления.

Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Создание формы MDI путем слияния меню и элементов управления ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="prerequisites"></a>Предварительные требования

Вам потребуется Visual Studio для выполнения этого пошагового руководства.

## <a name="create-the-project"></a>Создание проекта

1. В Visual Studio создайте проект приложения Windows с именем **MdiForm** (**файл** > **New** > **проекта**  >  **Visual C#**  или **Visual Basic** > **классический рабочий стол**  >   **Windows Forms Application**).

2. В конструкторе Windows Forms выберите форму.

3. В окне свойств установите для параметра <xref:System.Windows.Forms.Form.IsMdiContainer%2A> для `true`.

## <a name="create-the-main-menu"></a>Создание главного меню

Родительская форма MDI содержит главное меню. В главном меню есть один под названием **окно**. С помощью **окно** пункта меню, можно создать дочерние формы. Элементы меню из дочерних форм объединяются в главном меню.

1. Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> на форму.

2. Добавить <xref:System.Windows.Forms.ToolStripMenuItem> для <xref:System.Windows.Forms.MenuStrip> управления и назовите его **окно**.

3. Выберите элемент управления <xref:System.Windows.Forms.MenuStrip>.

4. В окне свойств установите для параметра <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> свойства `ToolStripMenuItem1`.

5. Добавьте подэлемент для **окно** пункта меню, а затем имя вложенного элемента **New**.

6. В окне «Свойства» щелкните **события**.

7. Дважды щелкните <xref:System.Windows.Forms.ToolStripItem.Click> событий.

     В конструкторе Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событий.

8. Вставьте следующий код в обработчик событий.

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>Добавить на панель элементов управления ToolStripPanel

При использовании <xref:System.Windows.Forms.MenuStrip> элементов управления с формой MDI, необходимо иметь <xref:System.Windows.Forms.ToolStripPanel> элемента управления. Необходимо добавить <xref:System.Windows.Forms.ToolStripPanel> управления **элементов** для создания формы MDI в конструкторе Windows Forms.

1. Откройте **элементов**, а затем нажмите кнопку **все формы Windows Forms** вкладка для отображения доступных элементов управления Windows Forms.

2. Щелкните правой кнопкой мыши, чтобы открыть контекстное меню и выберите **Выбор элементов**.

3. В **Выбор элементов панели элементов** диалоговое окно, прокрутите вниз **имя** столбца, пока не найдете **ToolStripPanel**.

4. Установите флажок рядом с **ToolStripPanel**, а затем нажмите кнопку **ОК**.

     <xref:System.Windows.Forms.ToolStripPanel> Появился на **элементов**.

## <a name="create-a-child-form"></a>Создание дочерней формы

В этой процедуре мы определим отдельный дочерний класс формы, имеет свой собственный <xref:System.Windows.Forms.MenuStrip> элемента управления. Пункты меню для этой формы объединяются с соответствующими родительской формы.

1. Добавьте новую форму с именем `ChildForm` в проект.

     Дополнительные сведения см. в разделе [Как Добавление в проект Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).

2. Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> управления дочерней формы.

3. Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), а затем выберите **изменение элементов**.

4. В **редактор коллекции элементов** диалоговое окно, добавьте новый <xref:System.Windows.Forms.ToolStripMenuItem> с именем **ChildMenuItem** в меню "дочерний".

     Дополнительные сведения см. в разделе [редактор коллекции элементов ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).

## <a name="test-the-form"></a>Проверить форму

1. Нажмите клавишу **F5** для компиляции и запуска в форму.

2. Нажмите кнопку **окно** пункт меню, чтобы открыть меню и нажмите кнопку **New**.

     Вы создадите новую дочернюю форму в клиентской области формы MDI. Меню дочерней формы объединяется с главного меню.

3. Закройте дочерней формы.

     Меню дочерней формы удаляется из главного меню.

4. Нажмите кнопку **New** несколько раз.

     Дочерние формы автоматически отображаются в категории **окно** пункт меню, поскольку <xref:System.Windows.Forms.MenuStrip> элемента управления <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> назначается свойство.

## <a name="add-toolstrip-support"></a>Добавить поддержку элемента управления ToolStrip

В этой процедуре вы добавите четыре <xref:System.Windows.Forms.ToolStrip> элементы управления для родительской формы MDI. Каждый <xref:System.Windows.Forms.ToolStrip> будет добавлен элемент управления внутри <xref:System.Windows.Forms.ToolStripPanel> элемент управления, который присоединяется к краю формы.

1. Из **элементов**, перетащите <xref:System.Windows.Forms.ToolStripPanel> на форму.

2. С помощью <xref:System.Windows.Forms.ToolStripPanel> выбран элемент управления, дважды щелкните <xref:System.Windows.Forms.ToolStrip> контролировать **элементов**.

     Объект <xref:System.Windows.Forms.ToolStrip> создается элемент управления в <xref:System.Windows.Forms.ToolStripPanel> элемента управления.

3. Выберите элемент управления <xref:System.Windows.Forms.ToolStripPanel>.

4. В окне «Свойства» измените значение элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Left>.

     <xref:System.Windows.Forms.ToolStripPanel> Управления фиксирует элемент управления у левого края формы под главным меню. Изменяет размер клиентской области MDI <xref:System.Windows.Forms.ToolStripPanel> элемента управления.

5. Повторите шаги 1 – 4.

     Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элемента управления в верхней части формы.

     <xref:System.Windows.Forms.ToolStripPanel> Прикреплен данный элемент управления под главным меню, но справа от первого <xref:System.Windows.Forms.ToolStripPanel> элемента управления. В этом разделе рассмотрены важность z порядка в правильной позиционирование <xref:System.Windows.Forms.ToolStripPanel> элементов управления.

6. Повторите шаги 1 – 4 для два раза <xref:System.Windows.Forms.ToolStripPanel> элементов управления.

     Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элементы управления справа и внизу формы.

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>Размещение элементов управления ToolStripPanel по оси Z

Положение закрепленного <xref:System.Windows.Forms.ToolStripPanel> управления в форме MDI определяется положением элемента управления в z порядке. Можно легко упорядочить z порядок элементов управления в окне "Структура документа".

1. В **представление** меню, щелкните **Other Windows**, а затем нажмите кнопку **Структура документа**.

     Расположение вашего <xref:System.Windows.Forms.ToolStripPanel> нестандартные элементы управления из предыдущей процедуры. Это обусловлено z порядок не верна. Используйте окно "Структура документа" для изменения z порядок элементов управления.

2. В окне «Структура документа» выберите **ToolStripPanel4**.

3. Нажмите кнопку со стрелкой вниз, пока **ToolStripPanel4** находится в нижней части списка.

     **ToolStripPanel4** прикреплен данный элемент управления в нижней части формы, под другими элементами управления.

4. Выберите **ToolStripPanel2**.

5. Нажмите кнопку со стрелкой вниз один раз для размещения элемента управления в-третьих, в списке.

     **ToolStripPanel2** прикреплен данный элемент управления в верхней части формы под главным меню и над другими элементами управления.

6. Выберите различные элементы управления в **Структура документа** окно и переместите их в разные положения в z порядка. Обратите внимание на результат z порядка при размещении закрепленных элементов управления. Нажмите CTRL-z или **отменить** на **изменить** меню, чтобы отменить внесенные изменения.

## <a name="checkpoint---test-your-form"></a>CHECKPOINT - тестирования в форму

1. Нажмите клавишу **F5** для компиляции и запуска в форму.

2. Нажмите кнопку захвата <xref:System.Windows.Forms.ToolStrip> управления и перетащите элемент управления в различных положениях на форме.

     Можно перетащить <xref:System.Windows.Forms.ToolStrip> управления от одного <xref:System.Windows.Forms.ToolStripPanel> элемента управления в другой.

## <a name="next-steps"></a>Следующие шаги

В этом пошаговом руководстве вы создали родительской формы MDI с <xref:System.Windows.Forms.ToolStrip> элементы управления и слияние меню. Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления, для многих других целей:

- Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>. Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).

- Создать форму с автоматически заполненные стандартным меню. Дополнительные сведения см. в разделе [Пошаговое руководство: Создание стандартных пунктов меню для формы](walkthrough-providing-standard-menu-items-to-a-form.md).

- Предоставить вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид. Дополнительные сведения см. в разделе [Как Назначение средства визуализации компоненту ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Практическое руководство. Создание родительских MDI-форм](../advanced/how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних MDI-форм](../advanced/how-to-create-mdi-child-forms.md)
- [Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [Элемент управления ToolStrip](toolstrip-control-windows-forms.md)
