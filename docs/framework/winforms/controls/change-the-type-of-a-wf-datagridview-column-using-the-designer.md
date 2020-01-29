---
title: Изменение типа столбца DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 976f257d38dc7be5c904e63da47c61486bd3301c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737132"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
Иногда может потребоваться изменить тип столбца, который уже был добавлен в Windows Forms элемент управления <xref:System.Windows.Forms.DataGridView>. Например, может потребоваться изменить типы некоторых столбцов, создаваемых автоматически при привязке элемента управления к источнику данных. Это полезно, когда отображаемая таблица содержит столбцы, содержащие внешние ключи, в строках связанной таблицы. В этом случае может потребоваться заменить столбцы текстового поля, отображающие эти внешние ключи, столбцами поля со списком, которые отображают более осмысленные значения из связанной таблицы.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Изменение типа столбца с помощью конструктора

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. В сетке **Свойства столбца** задайте для свойства `ColumnType` новый тип столбца.

    > [!NOTE]
    > Свойство `ColumnType` — это свойство только для времени разработки, указывающее класс, представляющий тип столбца. Это не фактическое свойство, определенное в классе столбца.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
