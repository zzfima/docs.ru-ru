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
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="c1984-102">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c1984-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="c1984-103">Для изменения строк и столбцов элементов управления можно <xref:System.Windows.Forms.TableLayoutPanel> использовать редактор коллекций элемента управления, называемый диалоговым окном **стили столбцов и строк** .</span><span class="sxs-lookup"><span data-stu-id="c1984-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="c1984-104">Если требуется, чтобы элемент управления занимал несколько строк или столбцов, установите `RowSpan` свойства и `ColumnSpan` в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c1984-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="c1984-105">Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)TableLayoutPanel.</span><span class="sxs-lookup"><span data-stu-id="c1984-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="c1984-106">Если необходимо выстроить элемент управления в пределах ячейки или нужно растянуть элемент управления внутри ячейки, используйте <xref:System.Windows.Forms.Control.Anchor%2A> свойство элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c1984-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="c1984-107">Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)TableLayoutPanel.</span><span class="sxs-lookup"><span data-stu-id="c1984-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="c1984-108">Изменение строк и столбцов</span><span class="sxs-lookup"><span data-stu-id="c1984-108">To edit rows and columns</span></span>

1. <span data-ttu-id="c1984-109">Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="c1984-109">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="c1984-110">![](./media/vs-winformsmttagglyph.gif "") <xref:System.Windows.Forms.TableLayoutPanel> Щелкните глиф смарт-тега элемента управления (глиф смарт-тега VS_WinFormSmtTagGlyph) и выберите изменить строки и столбцы, чтобы открыть диалоговое окно **стили столбцов и строк** .</span><span class="sxs-lookup"><span data-stu-id="c1984-110">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="c1984-111">Можно также щелкнуть правой кнопкой мыши <xref:System.Windows.Forms.TableLayoutPanel> элемент управления и выбрать пункт **изменить строки и столбцы** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="c1984-111">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="c1984-112">Чтобы добавить или удалить столбцы, выберите **столбцы** из раскрывающегося списка **тип элемента** .</span><span class="sxs-lookup"><span data-stu-id="c1984-112">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="c1984-113">Чтобы добавить или удалить строки, выберите **строки** из раскрывающегося списка **тип элемента** .</span><span class="sxs-lookup"><span data-stu-id="c1984-113">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="c1984-114">Нажмите кнопку **Добавить** , чтобы добавить строку или столбец в конец списка **элементов** .</span><span class="sxs-lookup"><span data-stu-id="c1984-114">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="c1984-115">Нажмите кнопку **Вставить** , чтобы добавить строку или столбец перед текущим выбранным элементом в списке.</span><span class="sxs-lookup"><span data-stu-id="c1984-115">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="c1984-116">При добавлении строки или столбца выберите **Тип размера** для новой строки или столбца.</span><span class="sxs-lookup"><span data-stu-id="c1984-116">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="c1984-117">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="c1984-117">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="c1984-118">Чтобы удалить строку или столбец, нажмите кнопку **Удалить** , чтобы удалить текущий выбранный элемент в списке **элементов** .</span><span class="sxs-lookup"><span data-stu-id="c1984-118">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1984-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c1984-119">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="c1984-120">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c1984-120">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
