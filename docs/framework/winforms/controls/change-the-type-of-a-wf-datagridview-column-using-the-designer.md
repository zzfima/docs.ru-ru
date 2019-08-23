---
title: Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e0b0b01a3c6da0680a3ec5fcd591344e04658a37
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917623"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
Иногда может потребоваться изменить тип столбца, который уже был добавлен в элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> . Например, может потребоваться изменить типы некоторых столбцов, создаваемых автоматически при привязке элемента управления к источнику данных. Это полезно, когда отображаемая таблица содержит столбцы, содержащие внешние ключи, в строках связанной таблицы. В этом случае может потребоваться заменить столбцы текстового поля, отображающие эти внешние ключи, столбцами поля со списком, которые отображают более осмысленные значения из связанной таблицы.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Изменение типа столбца с помощью конструктора

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. В сетке **Свойства столбца** задайте `ColumnType` для свойства новый тип столбца.

    > [!NOTE]
    > `ColumnType` Свойство является свойством, предназначенным только для времени разработки и указывающим класс, представляющий тип столбца. Это не фактическое свойство, определенное в классе столбца.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
