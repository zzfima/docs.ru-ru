---
title: Предотвращение добавления и удаления строк в элементе управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cca497aeaedd0c9f988241092eed707ecc259859
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628895"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора
Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>. Новые строки будут введены в специальную строку для новых записей в нижней части элемента управления. При отключении добавления строк строка для новых записей не отображается. После этого элемент управления можно сделать доступным только для чтения, отключив удаление строк и изменение ячеек.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-prevent-row-addition-and-deletion"></a>Предотвращение добавления и удаления строк

- Щелкните глиф действия конструктора (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем снимите флажки **включить добавление** и **включить удаление** .

    > [!NOTE]
    > Чтобы сделать элемент управления доступным только для чтения, снимите флажок **включить редактирование** .

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
