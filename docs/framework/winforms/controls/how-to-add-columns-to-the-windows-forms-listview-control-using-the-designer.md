---
title: Добавление столбцов в элемент управления ListView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744605"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Добавление столбцов в элемент управления ListView в формах Windows Forms с помощью конструктора

Элемент управления Windows Forms <xref:System.Windows.Forms.ListView> может отображать несколько столбцов для каждого элемента списка в представлении **Details** . Столбцы можно использовать для вывода нескольких типов сведений о каждом элементе списка. Например, список файлов может отображать имя файла, тип файла, размер и дату последнего изменения файла. Сведения о заполнении столбцов после их создания см. в разделе [инструкции. Отображение подэлементов в столбцах с помощью элемента управления ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ListView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-columns-in-the-designer"></a>Добавление столбцов в конструктор

1. В окне **Свойства** задайте для свойства <xref:System.Windows.Forms.ListView.View%2A> элемента управления значение <xref:System.Windows.Forms.View.Details>.

2. В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Columns%2A>.

     Откроется **Редактор коллекции колумнхеадер** .

3. Используйте кнопку **Добавить** , чтобы добавить новые столбцы. Затем можно выбрать заголовок столбца и задать его текст (заголовок столбца), выравнивание текста и ширину.

## <a name="see-also"></a>См. также:

- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
