---
title: Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: bf77cf3705a470bbe00be383f6a5cb2d28bda34d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039635"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора

При привязке Windows Forms <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных порядок вывода автоматически создаваемых столбцов определяется источником данных. Если этот порядок не является предпочтительным, можно изменить порядок столбцов с помощью конструктора. Кроме того, может потребоваться добавить в элемент управления несвязанные столбцы и изменить их порядок их вывода. Дополнительные сведения об изменении порядка столбцов программным способом см. в [разделе как Изменение порядка столбцов в элементе управления](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

## <a name="to-change-the-column-order-using-the-designer"></a>Изменение порядка столбцов с помощью конструктора

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. Щелкните стрелку вверх или вниз справа от списка **Выбранные столбцы** , пока выбранный столбец не будет расположен в нужном месте.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- [Практическое руководство. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
