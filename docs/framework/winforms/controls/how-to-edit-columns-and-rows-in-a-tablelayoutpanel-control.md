---
title: Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 4473b20eea57088104a51eb1b6c080219223d214
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628648"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel

Для изменения строк и столбцов элементов управления можно использовать редактор коллекций элемента управления <xref:System.Windows.Forms.TableLayoutPanel>, называемый диалоговым окном **стили столбцов и строк** .

> [!NOTE]
> Если требуется, чтобы элемент управления занимал несколько строк или столбцов, задайте свойства `RowSpan` и `ColumnSpan` элемента управления. Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).
>
> Если необходимо выстроить элемент управления в пределах ячейки или нужно растянуть элемент управления внутри ячейки, используйте свойство <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления. Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).

## <a name="to-edit-rows-and-columns"></a>Изменение строк и столбцов

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. Щелкните глиф действий конструктора <xref:System.Windows.Forms.TableLayoutPanel> элемента управления (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) и выберите **изменить строки и столбцы** , чтобы открыть диалоговое окно **стили столбцов и строк** . Можно также щелкнуть правой кнопкой мыши элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и выбрать пункт **изменить строки и столбцы** из контекстного меню.

3. Чтобы добавить или удалить столбцы, выберите **столбцы** из раскрывающегося списка **тип элемента** .

4. Чтобы добавить или удалить строки, выберите **строки** из раскрывающегося списка **тип элемента** .

5. Нажмите кнопку **Добавить** , чтобы добавить строку или столбец в конец списка **элементов** .

6. Нажмите кнопку **Вставить** , чтобы добавить строку или столбец перед текущим выбранным элементом в списке.

7. При добавлении строки или столбца выберите **Тип размера** для новой строки или столбца. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SizeType>.

8. Чтобы удалить строку или столбец, нажмите кнопку **Удалить** , чтобы удалить текущий выбранный элемент в списке **элементов** .

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.SizeType>
- [Элемент управления TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
