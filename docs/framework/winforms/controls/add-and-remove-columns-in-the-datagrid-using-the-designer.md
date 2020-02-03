---
title: Добавление и удаление столбцов элемента управления DataGridView с помощью конструктора
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 717a0074f0750352a23b90a9b6e5eab1dc6c925a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732345"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
Для вывода данных элемент управления <xref:System.Windows.Forms.DataGridView> Windows Forms должен содержать столбцы. Если планируется Ручное заполнение элемента управления, необходимо вручную добавить столбцы. Кроме того, можно привязать элемент управления к источнику данных, который автоматически создает и заполняет столбцы. Если источник данных содержит больше столбцов, чем требуется отобразить, можно удалить ненужные столбцы.

 Для следующих процедур требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-add-a-column-using-the-designer"></a>Добавление столбца с помощью конструктора

1. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **Добавить столбец**.

2. В диалоговом окне **Добавление столбца** выберите параметр **столбец с привязкой** к данным и выберите столбец из источника данных или выберите параметр **несвязанный столбец** и определите столбец с помощью предоставленных полей.

3. Нажмите кнопку **Добавить** , чтобы добавить столбец, в результате чего он появится в конструкторе, если существующие столбцы еще не заполнили область отображения элемента управления.

    > [!NOTE]
    > Свойства столбцов можно изменить в диалоговом окне **Изменение столбцов** , доступ к которому можно получить из смарт-тега элемента управления.

## <a name="to-remove-a-column-using-the-designer"></a>Удаление столбца с помощью конструктора

1. Выберите **изменить столбцы** из смарт-тега элемента управления.

2. Выберите столбец из списка **Выбранные столбцы** .

3. Нажмите кнопку **Удалить** , чтобы удалить столбец, что приведет к исчезновению его из конструктора.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
