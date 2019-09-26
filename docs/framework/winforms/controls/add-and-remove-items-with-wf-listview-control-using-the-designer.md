---
title: Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 62665746ea9fcd1553717b02b1f1349dc6415ab2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040085"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора

Процесс добавления элемента в элемент управления Windows Forms <xref:System.Windows.Forms.ListView> состоит в основном из указания элемента и присвоения ему свойств. Добавление или удаление элементов списка можно выполнить в любое время.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

### <a name="to-add-or-remove-items-using-the-designer"></a>Добавление или удаление элементов с помощью конструктора

1. Выберите элемент управления <xref:System.Windows.Forms.ListView>.

2. В окне " **Свойства** " нажмите кнопку **с многоточием** (![...) в окно свойств кнопки Visual Studio <xref:System.Windows.Forms.ListView.Items%2A> .](./media/visual-studio-ellipsis-button.png)) рядом со свойством.

     Откроется **Редактор коллекции ListViewItem** .

3. Чтобы добавить элемент, нажмите кнопку " **Добавить** ". Затем можно задать свойства нового элемента, например <xref:System.Windows.Forms.ListView.Text%2A> свойства и. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>

4. Чтобы удалить элемент, выберите его и нажмите кнопку **Удалить** .

## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление столбцов в Windows Forms элемент управления ListView](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение подэлементов в столбцах с Windows Forms элементом управления ListView](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков для элемента управления ListView Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Практическое руководство. Группирование элементов в элементе управления ListView Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
