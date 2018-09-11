---
title: Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 0480c8980f0eba17229fff0c1e947cac5216fb9e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275279"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора
Процесс добавления элемента в формы Windows <xref:System.Windows.Forms.ListView> элемент управления состоит в первую очередь определение элемента и назначение ему свойств. Добавление или удаление элементов списка можно сделать в любое время.  
  
 Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ListView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-items-using-the-designer"></a>Чтобы добавить или удалить элементы, с помощью конструктора  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.ListView>.  
  
2.  В **свойства** окно, нажмите кнопку **кнопку с многоточием** (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.ListView.Items%2A> свойство.  
  
     **Редактор коллекции ListViewItem** отображается.  
  
3.  Чтобы добавить элемент, щелкните **добавить** кнопки. Затем можно задать свойства нового элемента, такие как <xref:System.Windows.Forms.ListView.Text%2A> и <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> свойства.  
  
4.  Чтобы удалить элемент, выберите его и нажмите кнопку **удалить** кнопки.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)
