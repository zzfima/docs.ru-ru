---
title: Пошаговое руководство. Создание стандартных пунктов меню для формы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628778"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Пошаговое руководство. Создание стандартных пунктов меню для формы

С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.

В этом пошаговом руководстве показано, как использовать элемент управления <xref:System.Windows.Forms.MenuStrip> для создания стандартного меню. Форма также реагирует, когда пользователь выбирает пункт меню. В этом пошаговом руководстве показаны следующие задачи:

- Создание проекта Windows Forms.

- Создание стандартного меню.

- Создание элемента управления <xref:System.Windows.Forms.StatusStrip>.

- Обработка выбора пунктов меню.

По завершении у вас будет форма со стандартным меню, которое отображает элементы меню, выделенные в элементе управления <xref:System.Windows.Forms.StatusStrip>.

Чтобы скопировать код из этого раздела в виде одного списка, см. раздел [как предоставить стандартные пункты меню в форме](how-to-provide-standard-menu-items-to-a-form.md).

## <a name="prerequisites"></a>предварительные требования

Для выполнения этого пошагового руководства потребуется Visual Studio.

## <a name="create-the-project"></a>Создание проекта

1. В Visual Studio создайте проект приложения Windows с именем **стандардменуформ** (**File** > **New** > **Project** > **Visual C#**  или **Visual Basic** > **классический Настольный компьютер** > **приложение**).

2. В конструктор Windows Forms выберите форму.

## <a name="create-a-standard-menu"></a>Создание стандартного меню

Конструктор Windows Forms может автоматически заполнять элемент управления <xref:System.Windows.Forms.MenuStrip> с помощью стандартных пунктов меню.

1. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> на форму.

2. Щелкните глиф действий конструктора <xref:System.Windows.Forms.MenuStrip> элемента управления (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) и выберите **Вставить стандартные элементы**.

     Элемент управления <xref:System.Windows.Forms.MenuStrip> заполняется стандартными элементами меню.

3. Щелкните пункт меню **файл** , чтобы просмотреть элементы меню по умолчанию и соответствующие значки.

## <a name="create-a-statusstrip-control"></a>Создание элемента управления StatusStrip

Используйте элемент управления <xref:System.Windows.Forms.StatusStrip> для просмотра состояния приложений Windows Forms. В текущем примере пункты меню, выбранные пользователем, отображаются в элементе управления <xref:System.Windows.Forms.StatusStrip>.

1. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.StatusStrip> на форму.

     Элемент управления <xref:System.Windows.Forms.StatusStrip> автоматически закрепляется в нижней части формы.

2. Нажмите кнопку раскрывающегося списка <xref:System.Windows.Forms.StatusStrip> элемента управления и выберите **значение statuslabel как** , чтобы добавить элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> в элемент управления <xref:System.Windows.Forms.StatusStrip>.

## <a name="handle-item-selection"></a>Выбор элементов в обработке

Обработка события <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> для реагирования, когда пользователь выбирает пункт меню.

1. Щелкните элемент меню **файл** , созданный в разделе Создание стандартного меню.

2. В окне **Свойства** выберите **События**.

3. Дважды щелкните событие <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.

     Конструктор Windows Forms создает обработчик событий для события <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.

4. Вставьте следующий код в обработчик событий.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. Вставьте в форму определение метода служебной программы `UpdateStatus`.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>Контрольная точка — тестирование формы

1. Нажмите клавишу **F5** , чтобы скомпилировать и запустить форму.

2. Щелкните пункт меню **файл** , чтобы открыть меню.

3. В меню **файл** выберите один из элементов, чтобы выбрать его.

     Элемент управления <xref:System.Windows.Forms.StatusStrip> отображает выбранный элемент.

## <a name="next-steps"></a>Дальнейшие действия

В этом пошаговом руководстве вы создали форму со стандартным меню. Семейство элементов управления <xref:System.Windows.Forms.ToolStrip> можно использовать для многих других целей:

- Создайте контекстные меню для элементов управления с помощью <xref:System.Windows.Forms.ContextMenuStrip>. Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).

- Создание формы многодокументного интерфейса (MDI) с закреплением <xref:System.Windows.Forms.ToolStrip> элементов управления. Дополнительные сведения см. в разделе [Пошаговое руководство. Создание формы MDI с помощью слияния меню и элементов управления ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

- Придайте <xref:System.Windows.Forms.ToolStrip> элементам управления профессиональный внешний вид. Дополнительные сведения см. [в разделе как задать модуль подготовки отчетов ToolStrip для приложения](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Элемент управления MenuStrip](menustrip-control-windows-forms.md)
