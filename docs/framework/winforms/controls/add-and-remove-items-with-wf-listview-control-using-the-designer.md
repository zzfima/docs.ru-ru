---
title: Добавление и удаление элементов с помощью элемента управления ListView в конструкторе
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732298"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора

Процесс добавления элемента в элемент управления Windows Forms <xref:System.Windows.Forms.ListView> состоит главным образом из указания элемента и присвоения ему свойств. Добавление или удаление элементов списка можно выполнить в любое время.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ListView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-items-using-the-designer"></a>Добавление или удаление элементов с помощью конструктора

1. Выберите элемент управления <xref:System.Windows.Forms.ListView>.

2. В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Items%2A>.

     Откроется **Редактор коллекции ListViewItem** .

3. Чтобы добавить элемент, нажмите кнопку " **Добавить** ". Затем можно задать свойства нового элемента, например свойства <xref:System.Windows.Forms.ListView.Text%2A> и <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

4. Чтобы удалить элемент, выберите его и нажмите кнопку **Удалить** .

## <a name="see-also"></a>См. также:

- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
