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
ms.openlocfilehash: 99ff3286592da0a097835b8f35d687475ca54fb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040292"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel

Для изменения строк и столбцов элементов управления можно <xref:System.Windows.Forms.TableLayoutPanel> использовать редактор коллекций элемента управления, называемый диалоговым окном **стили столбцов и строк** .

> [!NOTE]
> Если требуется, чтобы элемент управления занимал несколько строк или столбцов, установите `RowSpan` свойства и `ColumnSpan` в элементе управления. Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)TableLayoutPanel.
>
> Если необходимо выстроить элемент управления в пределах ячейки или нужно растянуть элемент управления внутри ячейки, используйте <xref:System.Windows.Forms.Control.Anchor%2A> свойство элемента управления. Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)TableLayoutPanel.

## <a name="to-edit-rows-and-columns"></a>Изменение строк и столбцов

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. ![](./media/vs-winformsmttagglyph.gif "") <xref:System.Windows.Forms.TableLayoutPanel> Щелкните глиф смарт-тега элемента управления (глиф смарт-тега VS_WinFormSmtTagGlyph) и выберите изменить строки и столбцы, чтобы открыть диалоговое окно **стили столбцов и строк** . Можно также щелкнуть правой кнопкой мыши <xref:System.Windows.Forms.TableLayoutPanel> элемент управления и выбрать пункт **изменить строки и столбцы** из контекстного меню.

3. Чтобы добавить или удалить столбцы, выберите **столбцы** из раскрывающегося списка **тип элемента** .

4. Чтобы добавить или удалить строки, выберите **строки** из раскрывающегося списка **тип элемента** .

5. Нажмите кнопку **Добавить** , чтобы добавить строку или столбец в конец списка **элементов** .

6. Нажмите кнопку **Вставить** , чтобы добавить строку или столбец перед текущим выбранным элементом в списке.

7. При добавлении строки или столбца выберите **Тип размера** для новой строки или столбца. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SizeType>.

8. Чтобы удалить строку или столбец, нажмите кнопку **Удалить** , чтобы удалить текущий выбранный элемент в списке **элементов** .

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.SizeType>
- [Элемент управления TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
