---
title: Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: f47eb29bf9ae077555f352d10c667bac4ade9373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968325"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора
Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>. Новые строки будут введены в специальную строку для новых записей в нижней части элемента управления. При отключении добавления строк строка для новых записей не отображается. После этого элемент управления можно сделать доступным только для чтения, отключив удаление строк и изменение ячеек.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

## <a name="to-prevent-row-addition-and-deletion"></a>Предотвращение добавления и удаления строк

- Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем снимите флажки **включить добавление** и **включить удаление** .

    > [!NOTE]
    > Чтобы сделать элемент управления доступным только для чтения, снимите флажок **включить редактирование** .

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
