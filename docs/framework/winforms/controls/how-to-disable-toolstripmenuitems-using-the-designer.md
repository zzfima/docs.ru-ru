---
title: Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: fd80a6543c83ae957cd9c51b068d0702559f0925
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040269"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора
Вы можете ограничить или расширить команды, которые может выполнять пользователь, включив и отключив пункты меню в ответ на действия пользователя. Элементы меню включаются по умолчанию при их создании, но их можно изменить с помощью <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства. Вы можете управлять этим свойством во время разработки в окне **свойств** или программным путем, настроив его в коде. Дополнительные сведения см. в разделе [Практическое руководство. Отключите объектов ToolStripMenuItem](how-to-disable-toolstripmenuitems.md).

## <a name="to-disable-a-menu-item-at-design-time"></a>Отключение элемента меню во время разработки

1. Выбрав пункт меню в форме, задайте <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> для `false`свойства значение.

    > [!TIP]
    >  Отключение первого элемента меню или пункта верхнего уровня в меню отключает все пункты меню, содержащиеся в нем. Аналогично, отключение элемента меню с элементами подменю отключает элементы вложенного меню. Если для пользователя недоступны все команды в данном меню, рекомендуется как скрывать, так и отключать все меню, так как это представляет собой чистый пользовательский интерфейс. Следует скрывать и отключать меню, так как скрытие не запрещает доступ к команде меню с помощью сочетания клавиш. `false` Задайте для свойства пункта меню верхнего уровня значение, чтобы скрыть меню целиком. <xref:System.Windows.Forms.ToolStripItem.Visible%2A>

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Практическое руководство. Скрыть объектов ToolStripMenuItem](how-to-hide-toolstripmenuitems.md)
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
