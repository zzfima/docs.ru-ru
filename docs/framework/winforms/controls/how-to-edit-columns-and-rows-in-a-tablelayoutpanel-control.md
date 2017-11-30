---
title: "Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 84dbcfcbad30f9ef08548874c5e68ed658aa0914
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="5ec49-102">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ec49-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="5ec49-103">Можно использовать редактор коллекций элемента <xref:System.Windows.Forms.TableLayoutPanel> элемент управления с именем **стили столбцов и строк** диалоговое окно для редактирования строк и столбцов элементов управления.</span><span class="sxs-lookup"><span data-stu-id="5ec49-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ec49-104">Если требуется, чтобы элемент управления охватывал несколько строк или столбцов, задайте `RowSpan` и `ColumnSpan` свойства элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5ec49-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="5ec49-105">Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="5ec49-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="5ec49-106">Если вы хотите выравнивание элементов управления в ячейке или элемент управления, чтобы растянуть в ячейке, используйте элемент управления <xref:System.Windows.Forms.Control.Anchor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5ec49-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="5ec49-107">Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="5ec49-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="5ec49-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="5ec49-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5ec49-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="5ec49-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5ec49-110">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5ec49-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="5ec49-111">Для редактирования строк и столбцов</span><span class="sxs-lookup"><span data-stu-id="5ec49-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="5ec49-112">Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="5ec49-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="5ec49-113">Нажмите кнопку <xref:System.Windows.Forms.TableLayoutPanel> глиф смарт-тега элемента управления (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) и выберите **изменить строки и столбцы** Открытие  **Стили столбцов и строк** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5ec49-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="5ec49-114">Вы можете также щелкните правой кнопкой мыши <xref:System.Windows.Forms.TableLayoutPanel> управления и выберите **изменить строки и столбцы** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="5ec49-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="5ec49-115">Чтобы добавить или удалить столбцы, выберите **столбцы** из **тип члена** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="5ec49-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="5ec49-116">Чтобы добавить или удалить строки, выберите **строк** из **тип члена** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="5ec49-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="5ec49-117">Нажмите кнопку **добавить** кнопку, чтобы добавить строку или столбец в конец **член** списка.</span><span class="sxs-lookup"><span data-stu-id="5ec49-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="5ec49-118">Нажмите кнопку **вставить** кнопку, чтобы добавить строки или столбца перед выбранного элемента в списке.</span><span class="sxs-lookup"><span data-stu-id="5ec49-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="5ec49-119">При добавлении строки или столбца выберите **тип размера** для новой строки или столбца.</span><span class="sxs-lookup"><span data-stu-id="5ec49-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="5ec49-120">Для получения дополнительной информации см. <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="5ec49-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="5ec49-121">Чтобы удалить строку или столбец, щелкните **удалить** кнопку, чтобы удалить выбранный элемент в **член** списка.</span><span class="sxs-lookup"><span data-stu-id="5ec49-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec49-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5ec49-122">See Also</span></span>  
 <xref:System.Windows.Forms.SizeType>  
 [<span data-ttu-id="5ec49-123">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ec49-123">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
