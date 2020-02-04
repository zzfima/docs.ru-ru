---
title: Скрытие столбцов в элементе управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 3c9a6bdeacbeb5929488e6af0054403db73c4239
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738652"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
Иногда требуется показать только некоторые из столбцов, доступных в элементе управления <xref:System.Windows.Forms.DataGridView> Windows Forms. Например, можно отобразить столбец заработной платы сотрудника для пользователей с учетными данными управления, скрывая их от других пользователей. Кроме того, может потребоваться привязать элемент управления к источнику данных, содержащему много столбцов, только некоторые из которых нужно отобразить. В этом случае вы обычно удаляете столбцы, которые не нужны для отображения, а не скрывают их. Дополнительные сведения см. в разделе [инструкции. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора](add-and-remove-columns-in-the-datagrid-using-the-designer.md).

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-hide-a-column-using-the-designer"></a>Скрытие столбца с помощью конструктора

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. В сетке **Свойства столбца** задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> значение `false`.

    > [!NOTE]
    > Можно также скрыть столбец при его добавлении, сняв флажок **видимый** в диалоговом окне **Добавление столбца** .

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
