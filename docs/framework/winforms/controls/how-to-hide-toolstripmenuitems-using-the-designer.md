---
title: Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966620"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора
Скрытие пунктов меню — это способ управления пользовательским интерфейсом приложения и ограничения пользовательских команд. Часто требуется скрыть все меню, если все пункты меню на нем недоступны. Это приводит к уменьшению числа отсчетов пользователя. Кроме того, может потребоваться скрыть и отключить меню или пункт меню, так как скрытие одного из них не мешает пользователю получить доступ к команде меню с помощью сочетания клавиш. Дополнительные сведения об отключении пунктов меню см. [в разделе как Отключите объектов ToolStripMenuItem с помощью конструктора](how-to-disable-toolstripmenuitems-using-the-designer.md).

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Скрытие меню верхнего уровня и его пунктов подменю

1. Выберите пункт меню верхнего уровня и задайте для <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false`его свойства или <xref:System.Windows.Forms.ToolStripItem.Available%2A> значение.

     При скрытии пункта меню верхнего уровня все пункты меню в этом меню также скрываются. Если щелкнуть в любом месте <xref:System.Windows.Forms.MenuStrip> `false`, отличном от параметра <xref:System.Windows.Forms.ToolStripItem.Visible%2A> после установки значения, весь элемент меню верхнего уровня и его пункты подменю исчезают из формы, что показывает результат выполнения действия. Чтобы отобразить скрытый элемент меню верхнего уровня во время разработки, щелкните <xref:System.Windows.Forms.MenuStrip> в **области компонентов**, в **структуре документа**или в верхней части сетки свойств.

> [!NOTE]
> Вы редко скрываете все меню, за исключением дочерних меню многодокументного интерфейса (MDI) в сценарии слияния.

## <a name="to-hide-a-submenu-item"></a>Скрытие пункта подменю

1. Выберите элемент подменю и задайте для <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false`его свойства значение.

     При скрытии элемента вложенного меню он остается видимым в форме во время разработки, чтобы его можно было легко выбрать для дальнейшей работы. В действительности он будет скрыт во время выполнения.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
- [Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора](how-to-disable-toolstripmenuitems-using-the-designer.md)
