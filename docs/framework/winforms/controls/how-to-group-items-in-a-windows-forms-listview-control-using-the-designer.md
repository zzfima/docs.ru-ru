---
title: Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039402"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора

Функция группирования <xref:System.Windows.Forms.ListView> элемента управления позволяет отображать связанные наборы элементов в группах. Эти группы разделяются на экране горизонтальными заголовками групп, которые содержат заголовки групп. Группы можно использовать <xref:System.Windows.Forms.ListView> для упрощения навигации по большим спискам путем группировки элементов по алфавиту, по датам или по любой другой логической группировке. На следующем рисунке показаны некоторые сгруппированные элементы.

![Числа, разделенные на четные и четные группы.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

Чтобы включить группирование, необходимо сначала создать один или несколько <xref:System.Windows.Forms.ListViewGroup> объектов либо в конструкторе, либо программно. После определения группы можно назначить ей элементы.

> [!NOTE]
> <xref:System.Windows.Forms.ListView>группы доступны только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] том случае, <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> если приложение вызывает метод. В более ранних операционных системах любой код, связанный с группами, не оказывает никакого влияния, и группы не будут отображаться. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.

## <a name="to-add-or-remove-groups-in-the-designer"></a>Добавление или удаление групп в конструкторе

1. В окне **"свойства** " нажмите кнопку **с** многоточием![(...) в окно свойств кнопки Visual Studio <xref:System.Windows.Forms.ListView.Groups%2A> .](./media/visual-studio-ellipsis-button.png)) рядом со свойством.

     Откроется **Редактор коллекции листвиевграуп** .

2. Чтобы добавить группу, нажмите кнопку " **Добавить** ". Затем можно задать свойства новой группы, например <xref:System.Windows.Forms.ListViewGroup.Header%2A> свойства и. <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> Чтобы удалить группу, выберите ее и нажмите кнопку **Удалить** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>Назначение элементов группам в конструкторе

1. В окне **"свойства** " нажмите кнопку **с** многоточием![(...) в окно свойств кнопки Visual Studio <xref:System.Windows.Forms.ListView.Items%2A> .](./media/visual-studio-ellipsis-button.png)) рядом со свойством.

     Откроется **Редактор коллекции ListViewItem** .

2. Чтобы добавить новый элемент, нажмите кнопку " **Добавить** ". Затем можно задать свойства нового элемента, например <xref:System.Windows.Forms.ListViewItem.Text%2A> свойства и. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>

3. <xref:System.Windows.Forms.ListViewItem.Group%2A> Выберите свойство и выберите группу из раскрывающегося списка.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
