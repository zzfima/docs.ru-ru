---
title: Практическое руководство. Включение режима "только для чтения" для столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 82be9d31ff6bb3f2f5dd8a55b4426103d466bdd6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952096"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Включение режима "только для чтения" для столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
По умолчанию пользователи могут изменять текст и числовые данные, отображаемые <xref:System.Windows.Forms.DataGridView> в элементе управления Windows Forms. Если требуется отобразить данные, не предназначенные для изменения, необходимо сделать столбцы, содержащие данные, только для чтения. Сведения о том, как сделать элемент управления доступным только для чтения, см [. в разделе как Предотвращение добавления и удаления строк в элементе управления Windows Forms DataGridView с помощью конструктора](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>Создание столбца, доступного только для чтения, с помощью конструктора

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. В сетке **Свойства столбца** задайте <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> для `true`свойства значение.

    > [!NOTE]
    > Можно также сделать столбец только для чтения при его добавлении, установив флажок **только чтение** в диалоговом окне **Добавление столбца** .

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Практическое руководство. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Предотвращение добавления и удаления строк в элементе управления Windows Forms DataGridView с помощью конструктора](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
