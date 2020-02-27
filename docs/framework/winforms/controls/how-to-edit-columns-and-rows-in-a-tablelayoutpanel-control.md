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
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="765f2-102">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="765f2-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="765f2-103">Для изменения строк и столбцов элементов управления можно использовать редактор коллекций элемента управления <xref:System.Windows.Forms.TableLayoutPanel>, называемый диалоговым окном **стили столбцов и строк** .</span><span class="sxs-lookup"><span data-stu-id="765f2-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="765f2-104">Если требуется, чтобы элемент управления занимал несколько строк или столбцов, задайте свойства `RowSpan` и `ColumnSpan` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="765f2-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="765f2-105">Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="765f2-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="765f2-106">Если необходимо выстроить элемент управления в пределах ячейки или нужно растянуть элемент управления внутри ячейки, используйте свойство <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="765f2-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="765f2-107">Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="765f2-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="765f2-108">Изменение строк и столбцов</span><span class="sxs-lookup"><span data-stu-id="765f2-108">To edit rows and columns</span></span>

1. <span data-ttu-id="765f2-109">Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="765f2-109">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="765f2-110">Щелкните глиф действий конструктора <xref:System.Windows.Forms.TableLayoutPanel> элемента управления (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) и выберите **изменить строки и столбцы** , чтобы открыть диалоговое окно **стили столбцов и строк** .</span><span class="sxs-lookup"><span data-stu-id="765f2-110">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="765f2-111">Можно также щелкнуть правой кнопкой мыши элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и выбрать пункт **изменить строки и столбцы** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="765f2-111">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="765f2-112">Чтобы добавить или удалить столбцы, выберите **столбцы** из раскрывающегося списка **тип элемента** .</span><span class="sxs-lookup"><span data-stu-id="765f2-112">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="765f2-113">Чтобы добавить или удалить строки, выберите **строки** из раскрывающегося списка **тип элемента** .</span><span class="sxs-lookup"><span data-stu-id="765f2-113">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="765f2-114">Нажмите кнопку **Добавить** , чтобы добавить строку или столбец в конец списка **элементов** .</span><span class="sxs-lookup"><span data-stu-id="765f2-114">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="765f2-115">Нажмите кнопку **Вставить** , чтобы добавить строку или столбец перед текущим выбранным элементом в списке.</span><span class="sxs-lookup"><span data-stu-id="765f2-115">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="765f2-116">При добавлении строки или столбца выберите **Тип размера** для новой строки или столбца.</span><span class="sxs-lookup"><span data-stu-id="765f2-116">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="765f2-117">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="765f2-117">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="765f2-118">Чтобы удалить строку или столбец, нажмите кнопку **Удалить** , чтобы удалить текущий выбранный элемент в списке **элементов** .</span><span class="sxs-lookup"><span data-stu-id="765f2-118">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="765f2-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="765f2-119">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="765f2-120">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="765f2-120">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
