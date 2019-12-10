---
title: Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 03958109d4daa3fc369660de66973bb659e29c60
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960176"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора

Функция группирования элемента управления <xref:System.Windows.Forms.ListView> позволяет отображать связанные наборы элементов в группах. Эти группы разделяются на экране горизонтальными заголовками групп, которые содержат заголовки групп. Вы можете использовать группы <xref:System.Windows.Forms.ListView>, чтобы упростить навигацию по большим спискам, группируя элементы по алфавиту, по датам или по любой другой логической группировке. На следующем рисунке показаны некоторые сгруппированные элементы.

![Числа, разделенные на четные и четные группы.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ListView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

Чтобы включить группирование, необходимо сначала создать один или несколько объектов <xref:System.Windows.Forms.ListViewGroup> в конструкторе или программно. После определения группы можно назначить ей элементы.

## <a name="to-add-or-remove-groups-in-the-designer"></a>Добавление или удаление групп в конструкторе

1. В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Groups%2A>.

     Откроется **Редактор коллекции листвиевграуп** .

2. Чтобы добавить группу, нажмите кнопку " **Добавить** ". Затем можно задать свойства новой группы, например свойства <xref:System.Windows.Forms.ListViewGroup.Header%2A> и <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>. Чтобы удалить группу, выберите ее и нажмите кнопку **Удалить** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>Назначение элементов группам в конструкторе

1. В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Items%2A>.

     Откроется **Редактор коллекции ListViewItem** .

2. Чтобы добавить новый элемент, нажмите кнопку " **Добавить** ". Затем можно задать свойства нового элемента, например свойства <xref:System.Windows.Forms.ListViewItem.Text%2A> и <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

3. Выберите свойство <xref:System.Windows.Forms.ListViewItem.Group%2A> и выберите группу из раскрывающегося списка.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
