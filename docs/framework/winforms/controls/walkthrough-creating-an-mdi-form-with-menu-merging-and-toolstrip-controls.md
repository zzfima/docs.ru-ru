---
title: Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip
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
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628791"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip

Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> поддерживает приложения с интерфейсом MDI, а элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает слияние меню. Формы MDI также могут содержать элементы управления <xref:System.Windows.Forms.ToolStrip>.

В этом пошаговом руководстве показано, как использовать элементы управления <xref:System.Windows.Forms.ToolStripPanel> с формой MDI. Форма также поддерживает слияние меню с вложенными меню. В этом пошаговом руководстве показаны следующие задачи:

- Создание проекта Windows Forms.

- Создание главного меню для формы. Фактическое имя меню будет разным.

- Добавление элемента управления <xref:System.Windows.Forms.ToolStripPanel> на **панель элементов**.

- Создание дочерней формы.

- Упорядочение элементов управления <xref:System.Windows.Forms.ToolStripPanel> по z-порядку.

По завершении у вас будет форма MDI, поддерживающая слияние меню и перемещаемые элементы управления <xref:System.Windows.Forms.ToolStrip>.

Чтобы скопировать код из этого раздела в виде одного списка, см. раздел [как создать форму MDI с помощью слияния меню и элементов управления ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="prerequisites"></a>предварительные требования

Для выполнения этого пошагового руководства потребуется Visual Studio.

## <a name="create-the-project"></a>Создание проекта

1. В Visual Studio создайте проект приложения Windows с именем **мдиформ** (**File** > **New** > **Project** > **Visual C#**  или **Visual Basic** > **классический Настольный компьютер** > **приложение**).

2. В конструктор Windows Forms выберите форму.

3. В окно свойств задайте для <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.

## <a name="create-the-main-menu"></a>Создание главного меню

Родительская форма MDI содержит главное меню. Главное меню содержит один пункт меню « **окно»** . С помощью пункта меню « **окно** » можно создавать дочерние формы. Пункты меню из дочерних форм объединяются в главное меню.

1. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> на форму.

2. Добавьте <xref:System.Windows.Forms.ToolStripMenuItem> в элемент управления <xref:System.Windows.Forms.MenuStrip> и присвойте ему имя **Window**.

3. Выберите элемент управления <xref:System.Windows.Forms.MenuStrip>.

4. В окно свойств задайте для свойства <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> значение `ToolStripMenuItem1`.

5. Добавьте подэлемент в пункт меню **окно** , а затем назовите **Новый**подэлемент.

6. В окно свойств щелкните **события**.

7. Дважды щелкните событие <xref:System.Windows.Forms.ToolStripItem.Click>.

     Конструктор Windows Forms создает обработчик событий для события <xref:System.Windows.Forms.ToolStripItem.Click>.

8. Вставьте следующий код в обработчик событий.

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>Добавление элемента управления ToolStripPanel на панель элементов

При использовании <xref:System.Windows.Forms.MenuStrip> элементов управления с формой MDI необходимо иметь элемент управления <xref:System.Windows.Forms.ToolStripPanel>. Чтобы создать форму MDI в конструктор Windows Forms, необходимо добавить элемент управления <xref:System.Windows.Forms.ToolStripPanel> на **панель элементов** .

1. Откройте **панель элементов**и перейдите на вкладку **все Windows Forms** , чтобы отобразить доступные элементы управления Windows Forms.

2. Щелкните правой кнопкой мыши, чтобы открыть контекстное меню, и выберите **пункт Выбрать элементы**.

3. В диалоговом окне **Выбор элементов панели элементов** прокрутите вниз столбец **имя** , пока не найдете элемент **ToolStripPanel**.

4. Установите **флажок рядом с полем, а**затем нажмите кнопку **ОК**.

     Элемент управления <xref:System.Windows.Forms.ToolStripPanel> появится в **области элементов**.

## <a name="create-a-child-form"></a>Создание дочерней формы

В этой процедуре будет определен отдельный класс дочерней формы, имеющий собственный элемент управления <xref:System.Windows.Forms.MenuStrip>. Элементы меню для этой формы объединяются с элементами родительской формы.

1. Добавьте в проект новую форму с именем `ChildForm`.

     Дополнительные сведения см. [в разделе инструкции. добавление Windows Forms в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).

2. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> на дочернюю форму.

3. Щелкните глиф действий конструктора <xref:System.Windows.Forms.MenuStrip> элемента управления (![маленькая черная стрелка](./media/designer-actions-glyph.gif)), а затем выберите **изменить элементы**.

4. В диалоговом окне **Редактор коллекции элементов** добавьте новый <xref:System.Windows.Forms.ToolStripMenuItem> с именем **чилдменуитем** в дочернее меню.

     Дополнительные сведения см. в статье [Редактор коллекции элементов ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).

## <a name="test-the-form"></a>Тестирование формы

1. Нажмите клавишу **F5** , чтобы скомпилировать и запустить форму.

2. Щелкните пункт меню **окно** , чтобы открыть меню, и выберите пункт **создать**.

     Новая дочерняя форма создается в клиентской области MDI формы. Меню дочерней формы объединяется с главным меню.

3. Закройте дочернюю форму.

     Меню дочерней формы удаляется из главного меню.

4. Нажмите кнопку **создать** несколько раз.

     Дочерние формы автоматически перечисляются под элементом меню « **окно»** , поскольку назначено свойство <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> <xref:System.Windows.Forms.MenuStrip> элемента управления.

## <a name="add-toolstrip-support"></a>Добавление поддержки ToolStrip

В этой процедуре в родительскую MDI-форму будут добавлены четыре элемента управления <xref:System.Windows.Forms.ToolStrip>. Каждый элемент управления <xref:System.Windows.Forms.ToolStrip> добавляется в элемент управления <xref:System.Windows.Forms.ToolStripPanel>, закрепленный за границей формы.

1. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.ToolStripPanel> на форму.

2. Выбрав элемент управления <xref:System.Windows.Forms.ToolStripPanel>, дважды щелкните элемент управления <xref:System.Windows.Forms.ToolStrip> на **панели элементов**.

     Элемент управления <xref:System.Windows.Forms.ToolStrip> создается в элементе управления <xref:System.Windows.Forms.ToolStripPanel>.

3. Выберите элемент управления <xref:System.Windows.Forms.ToolStripPanel>.

4. В окно свойств измените значение свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления на <xref:System.Windows.Forms.DockStyle.Left>.

     Элемент управления <xref:System.Windows.Forms.ToolStripPanel> закрепляется в левой части формы под главным меню. Размер клиентской области MDI изменяется в соответствии с элементом управления <xref:System.Windows.Forms.ToolStripPanel>.

5. Повторите шаги с 1 по 4.

     Закрепите новый элемент управления <xref:System.Windows.Forms.ToolStripPanel> в верхней части формы.

     Элемент управления <xref:System.Windows.Forms.ToolStripPanel> закреплен под главным меню, а справа от первого элемента управления <xref:System.Windows.Forms.ToolStripPanel>. Этот шаг иллюстрирует важность z-порядка при правильном размещении <xref:System.Windows.Forms.ToolStripPanel> элементов управления.

6. Повторите шаги с 1 по 4 для двух дополнительных <xref:System.Windows.Forms.ToolStripPanel> элементов управления.

     Закрепите новые элементы управления <xref:System.Windows.Forms.ToolStripPanel> в правой и нижней части формы.

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>Упорядочить элементы управления ToolStripPanel по Z-порядку

Положение закрепленного <xref:System.Windows.Forms.ToolStripPanel> элемента управления в форме MDI определяется положением элемента управления в z-порядке. Z-порядок элементов управления можно легко упорядочить в окне "Структура документа".

1. В меню **вид** выберите **другие окна**, а затем щелкните **Структура документа**.

     Размещение элементов управления <xref:System.Windows.Forms.ToolStripPanel> из предыдущей процедуры является нестандартным. Это обусловлено неправильным z-порядком. Используйте окно "Структура документа", чтобы изменить z-порядок элементов управления.

2. В окне Структура документа выберите **ToolStripPanel4**.

3. Несколько раз нажмите кнопку со стрелкой вниз, чтобы **ToolStripPanel4** в нижней части списка.

     Элемент управления **ToolStripPanel4** закрепляется в нижней части формы под другими элементами управления.

4. Выберите **ToolStripPanel2**.

5. Нажмите кнопку со стрелкой вниз один раз, чтобы разместить третий элемент управления в списке.

     Элемент управления **ToolStripPanel2** закрепляется в верхней части формы, под главным меню и над другими элементами управления.

6. Выберите различные элементы управления в окне " **Структура документа** " и переместите их в различные позиции в z-порядке. Обратите внимание на результат z-порядка размещения закрепленных элементов управления. Для отмены изменений используйте сочетание клавиш CTRL-Z или **отменить** в меню **Правка** .

## <a name="checkpoint---test-your-form"></a>Контрольная точка — тестирование формы

1. Нажмите клавишу **F5** , чтобы скомпилировать и запустить форму.

2. Щелкните захват элемента управления <xref:System.Windows.Forms.ToolStrip> и перетащите элемент управления в другое положение в форме.

     Элемент управления <xref:System.Windows.Forms.ToolStrip> можно перетащить из одного элемента управления <xref:System.Windows.Forms.ToolStripPanel> в другой.

## <a name="next-steps"></a>Дальнейшие действия

В этом пошаговом руководстве вы создали родительскую MDI-форму с <xref:System.Windows.Forms.ToolStrip> элементами управления и слиянием меню. Семейство элементов управления <xref:System.Windows.Forms.ToolStrip> можно использовать для многих других целей:

- Создайте контекстные меню для элементов управления с помощью <xref:System.Windows.Forms.ContextMenuStrip>. Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).

- Создана форма с автоматически заполненным стандартным меню. Дополнительные сведения см. в разделе [Пошаговое руководство. предоставление стандартных пунктов меню в форме](walkthrough-providing-standard-menu-items-to-a-form.md).

- Придайте <xref:System.Windows.Forms.ToolStrip> элементам управления профессиональный внешний вид. Дополнительные сведения см. [в разделе как задать модуль подготовки отчетов ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Практическое руководство. Создание родительских MDI-форм](../advanced/how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних MDI-форм](../advanced/how-to-create-mdi-child-forms.md)
- [Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [Элемент управления ToolStrip](toolstrip-control-windows-forms.md)
