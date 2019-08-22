---
title: Практическое руководство. Добавление столбцов в элемент управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 10963fcb6d87ed74f73ecf4f1831a56eae5a392d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658461"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Добавление столбцов в элемент управления ListView в формах Windows Forms с помощью конструктора

Элемент управления <xref:System.Windows.Forms.ListView> Windows Forms может отображать несколько столбцов для каждого элемента списка в представлении **Details** . Столбцы можно использовать для вывода нескольких типов сведений о каждом элементе списка. Например, список файлов может отображать имя файла, тип файла, размер и дату последнего изменения файла. Сведения о заполнении столбцов после их создания см. в разделе [как Отображение подэлементов в столбцах с Windows Forms элементом управления](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)ListView.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

### <a name="to-add-columns-in-the-designer"></a>Добавление столбцов в конструктор

1. В окне **Свойства** присвойте <xref:System.Windows.Forms.ListView.View%2A> свойству <xref:System.Windows.Forms.View.Details>элемента управления значение.

2. В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств Visual <xref:System.Windows.Forms.ListView.Columns%2A> Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством.

     Откроется **Редактор коллекции колумнхеадер** .

3. Используйте кнопку **Добавить** , чтобы добавить новые столбцы. Затем можно выбрать заголовок столбца и задать его текст (заголовок столбца), выравнивание текста и ширину.

## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение подэлементов в столбцах с Windows Forms элементом управления ListView](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков для элемента управления ListView Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
