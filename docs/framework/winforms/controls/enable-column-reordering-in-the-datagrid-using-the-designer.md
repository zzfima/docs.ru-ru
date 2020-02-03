---
title: Включение изменения порядка столбцов в элементе управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 823c0064b2710ab5dfd0f67edf95374590d4490b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745841"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
При просмотре данных, отображаемых в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>, пользователям иногда требуется сравнить значения в конкретных столбцах. Это может оказаться неудобным, если столбцы широко разделены в элементе управления, особенно если для просмотра всех интересующих вас столбцов пользователи должны прокручиваться по горизонтали. Можно упростить задачу сравнения значений столбцов, позволяя пользователям изменять порядок столбцов. При включении переупорядочения столбцов пользователи могут перемещать столбец в новую точку, перетаскивая заголовок столбца с помощью мыши.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-enable-column-reordering"></a>Включение изменения порядка столбцов

- Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **включить изменение порядка столбцов**.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
