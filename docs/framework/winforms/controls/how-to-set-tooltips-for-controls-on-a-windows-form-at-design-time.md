---
title: Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211689"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Практическое руководство. Определение всплывающих подсказок для элементов управления формы Windows во время разработки

Можно задать <xref:System.Windows.Forms.ToolTip> строку в коде или в конструкторе Windows Forms в Visual Studio. Дополнительные сведения о <xref:System.Windows.Forms.ToolTip> компонента, см. в разделе [Общие сведения о компоненте ToolTip](tooltip-component-overview-windows-forms.md).

## <a name="set-a-tooltip-programmatically"></a>Для задания подсказки программным способом

1. Добавьте элемент управления, который будет отображаться объект ToolTip.

2. Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a>Для задания подсказки в конструкторе

1. В Visual Studio добавьте <xref:System.Windows.Forms.ToolTip> в форму компонент.

2. Выберите элемент управления, который будет отображаться объект ToolTip, или добавьте его в форму.

3. В **свойства** окне **во всплывающей подсказке над ToolTip1** значение соответствующую строку текста.

### <a name="to-remove-a-tooltip-programmatically"></a>Чтобы удалить подсказки программными средствами

1. Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a>Удалить подсказки в конструкторе

1. В Visual Studio выберите элемент управления, который отображает подсказку.

2. В **свойства** окно, удалите текст в **во всплывающей подсказке над ToolTip1**.

## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления ToolTip](tooltip-component-overview-windows-forms.md)
- [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [Компонент ToolTip](tooltip-component-windows-forms.md)
