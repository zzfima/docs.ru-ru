---
title: Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: e5069dd46a31a65f65a17d750b685d82762e3d11
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038208"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.

Неотъемлемой частью <xref:System.Windows.Forms.ToolBar> элемента управления являются кнопки, добавленные в него. Они могут использоваться для предоставления простого доступа к командам меню или, Кроме того, можно поместить в другую область пользовательского интерфейса приложения, чтобы предоставить пользователям команды, недоступные в структуре меню.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ToolBar> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.


### <a name="to-add-buttons-at-design-time"></a>Добавление кнопок во время разработки

1. Выберите элемент управления <xref:System.Windows.Forms.ToolBar>.

2. В окне **Свойства** щелкните <xref:System.Windows.Forms.ToolBar.Buttons%2A> свойство, чтобы выбрать его, и нажмите кнопку **с многоточием** ![(...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)), чтобы открыть **ToolBarButton Редактор коллекций**.

3. Используйте кнопки **Добавить** и **Удалить** для добавления и удаления <xref:System.Windows.Forms.ToolBar> кнопок из элемента управления.

4. Настройте свойства отдельных кнопок в окне **Свойства** , которое отображается на панели в правой части редактора. В следующей таблице приведены некоторые важные свойства, которые следует учитывать.

    |Свойство.|Описание|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Задает меню, отображаемое в раскрывающейся кнопке панели инструментов. <xref:System.Windows.Forms.ToolBarButton.Style%2A> Свойство кнопки панели инструментов должно иметь <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>значение. Это свойство принимает экземпляр <xref:System.Windows.Forms.ContextMenu> класса в качестве ссылки.|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Задает, является ли кнопка на панели инструментов частичной. <xref:System.Windows.Forms.ToolBarButton.Style%2A> Свойство кнопки панели инструментов должно иметь <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>значение.|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Определяет, находится ли кнопка-переключатель в данный момент в состоянии "Отправлено". <xref:System.Windows.Forms.ToolBarButton.Style%2A> Свойству кнопки панели инструментов должно быть <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> присвоено <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>значение или.|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Задает стиль кнопки панели инструментов. Должно быть одним из значений в <xref:System.Windows.Forms.ToolBarButtonStyle> перечислении.|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Текстовая строка, отображаемая кнопкой.|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Текст, отображаемый в виде всплывающей подсказки для кнопки.|

5. Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно и создать указанные панели.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolBar>
- [Практическое руководство. Определение значка для кнопки на панели инструментов](how-to-define-an-icon-for-a-toolbar-button.md)
- [Практическое руководство. События меню триггера для кнопок панели инструментов](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Общие сведения об элементе управления ToolBar](toolbar-control-overview-windows-forms.md)
- [Элемент управления ToolBar](toolbar-control-windows-forms.md)
