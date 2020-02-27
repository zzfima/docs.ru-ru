---
title: Сделать столбцы доступны только для чтения в элементе управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 2dd3f8bfcad39ca3d530c79a6e6a8170585f7adf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627959"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора
По умолчанию пользователи могут изменять текст и числовые данные, отображаемые в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>. Если требуется отобразить данные, не предназначенные для изменения, необходимо сделать столбцы, содержащие данные, только для чтения. Сведения о том, как сделать элемент управления доступным только для чтения, см. в разделе [как предотвратить добавление и удаление строк в элементе управления Windows Forms DataGridView с помощью конструктора](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>Создание столбца, доступного только для чтения, с помощью конструктора

1. Щелкните глиф действия конструктора (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. В сетке **Свойства столбца** задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> значение `true`.

    > [!NOTE]
    > Можно также сделать столбец только для чтения при его добавлении, установив флажок **только чтение** в диалоговом окне **Добавление столбца** .

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
