---
title: Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666206"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.

<xref:System.Windows.Forms.ToolBar>кнопки могут отображать значки в них для простоты идентификации пользователями. Это достигается путем добавления изображений в <xref:System.Windows.Forms.ImageList> компонент и их связывания <xref:System.Windows.Forms.ToolBar> с элементом управления.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ToolBar> элемент управления и <xref:System.Windows.Forms.ImageList> компонент. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Задание значка для кнопки панели инструментов во время разработки

1. Добавление изображений в <xref:System.Windows.Forms.ImageList> компонент. Дополнительные сведения см. в разделе [Практическое руководство. Добавление или удаление изображений ImageList с помощью конструктора](how-to-add-or-remove-imagelist-images-with-the-designer.md).

2. <xref:System.Windows.Forms.ToolBar> Выберите элемент управления в форме.

3. В окне **Свойства** задайте <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ImageList> компоненту <xref:System.Windows.Forms.ToolBar.ImageList%2A> свойство элемента управления.

4. ![](./media/visual-studio-ellipsis-button.png)Щелкните свойство элементауправления,чтобывыбратьего,инажмитекнопкусмноготочием(...)вокносвойствкнопкиVisualStudio.),чтобыоткрытьредакторколлекцииToolBarButton.<xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.Buttons%2A>

5. Используйте кнопку **Добавить** , чтобы добавить кнопки в <xref:System.Windows.Forms.ToolBar> элемент управления.

6. В окне **Свойства** , которое отображается в правой части окна **Редактор коллекции ToolBarButton** <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> , задайте для свойства каждой кнопки панели инструментов одно из значений в списке, которое отображается из изображений, добавленных в <xref:System.Windows.Forms.ImageList> компонент.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolBar>
- [Практическое руководство. События меню триггера для кнопок панели инструментов](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Элемент управления ToolBar](toolbar-control-windows-forms.md)
- [Компонент ImageList](imagelist-component-windows-forms.md)
