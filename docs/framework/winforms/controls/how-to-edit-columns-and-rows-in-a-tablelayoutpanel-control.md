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
ms.openlocfilehash: 820d2f98290650bfaf377bd2d4b863dfb2e6e704
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500788"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="18906-102">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="18906-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="18906-103">Можно использовать редактор коллекции для <xref:System.Windows.Forms.TableLayoutPanel> элементом управления, называемым **стили столбцов и строк** диалоговое окно для редактирования строк и столбцов элементов управления.</span><span class="sxs-lookup"><span data-stu-id="18906-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18906-104">Элемент управления, чтобы охватывать несколько строк или столбцов, задайте `RowSpan` и `ColumnSpan` свойствам элемента управления.</span><span class="sxs-lookup"><span data-stu-id="18906-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="18906-105">Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="18906-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="18906-106">Если вы хотите выравнивание элементов управления внутри ячейки или элемент управления выполнить растяжение в ячейке, использование элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="18906-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="18906-107">Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="18906-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="18906-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="18906-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="18906-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="18906-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="18906-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="18906-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="18906-111">Чтобы изменить строки и столбцы</span><span class="sxs-lookup"><span data-stu-id="18906-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="18906-112">Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="18906-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="18906-113">Нажмите кнопку <xref:System.Windows.Forms.TableLayoutPanel> глиф смарт-тега элемента управления (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) и выберите **изменить строки и столбцы** открыть  **Стили столбцов и строк** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="18906-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="18906-114">Вы можете также щелкнуть правой кнопкой мыши <xref:System.Windows.Forms.TableLayoutPanel> управления и выберите **изменить строки и столбцы** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="18906-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="18906-115">Чтобы добавить или удалить столбцы, выберите **столбцы** из **тип члена** поле с раскрывающимся списком.</span><span class="sxs-lookup"><span data-stu-id="18906-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="18906-116">Чтобы добавить или удалить строки, выберите **строк** из **тип члена** поле с раскрывающимся списком.</span><span class="sxs-lookup"><span data-stu-id="18906-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="18906-117">Нажмите кнопку **добавить** , чтобы добавить в конец строки или столбца **член** списка.</span><span class="sxs-lookup"><span data-stu-id="18906-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="18906-118">Нажмите кнопку **вставить** кнопку, чтобы добавить строки или столбца перед текущего выбранного элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="18906-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="18906-119">При добавлении строки или столбца, выберите **тип размера** для новой строки или столбца.</span><span class="sxs-lookup"><span data-stu-id="18906-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="18906-120">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="18906-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="18906-121">Чтобы удалить строки или столбца, щелкните **удалить** кнопку, чтобы удалить выбранный элемент в **член** списка.</span><span class="sxs-lookup"><span data-stu-id="18906-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18906-122">См. также</span><span class="sxs-lookup"><span data-stu-id="18906-122">See Also</span></span>  
 <xref:System.Windows.Forms.SizeType>  
 [<span data-ttu-id="18906-123">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="18906-123">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
