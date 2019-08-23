---
title: Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 7a3029192ab0da4a954dfd7d3d258a00b154924e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957115"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
Для вывода <xref:System.Windows.Forms.DataGridView> данных элемент управления Windows Forms должен содержать столбцы. Если планируется Ручное заполнение элемента управления, необходимо вручную добавить столбцы. Кроме того, можно привязать элемент управления к источнику данных, который автоматически создает и заполняет столбцы. Если источник данных содержит больше столбцов, чем требуется отобразить, можно удалить ненужные столбцы.

 Для следующих процедур требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

## <a name="to-add-a-column-using-the-designer"></a>Добавление столбца с помощью конструктора

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **Добавить столбец**.

2. В диалоговом окне **Добавление столбца** выберите параметр **столбец с привязкой** к данным и выберите столбец из источника данных или выберите параметр несвязанный **столбец** и определите столбец с помощью предоставленных полей.

3. Нажмите кнопку **Добавить** , чтобы добавить столбец, в результате чего он появится в конструкторе, если существующие столбцы еще не заполнили область отображения элемента управления.

    > [!NOTE]
    > Свойства столбцов можно изменить в диалоговом окне **Изменение столбцов** , доступ к которому можно получить из смарт-тега элемента управления.

## <a name="to-remove-a-column-using-the-designer"></a>Удаление столбца с помощью конструктора

1. Выберите **изменить столбцы** из смарт-тега элемента управления.

2. Выберите столбец из списка **Выбранные столбцы** .

3. Нажмите кнопку **Удалить** , чтобы удалить столбец, что приведет к исчезновению его из конструктора.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
