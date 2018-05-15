---
title: Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 4c284e9d2798a1992e3152a85eca47c8d33bfde8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="f69c3-102">Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69c3-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="f69c3-103">В представлении сведений о <xref:System.Windows.Forms.ListView> элемент управления может отображать несколько столбцов для каждого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="f69c3-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="f69c3-104">Можно использовать столбцы для отображения пользователю нескольких типов данных о каждом элементе списка.</span><span class="sxs-lookup"><span data-stu-id="f69c3-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="f69c3-105">Например в списке файлов можно отображать имя файла, тип файла, размер и Дата последнего изменения файла.</span><span class="sxs-lookup"><span data-stu-id="f69c3-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="f69c3-106">Сведения о заполнении столбцов после их создания см. в разделе [как: отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f69c3-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="f69c3-107">Чтобы добавить столбцы программными средствами</span><span class="sxs-lookup"><span data-stu-id="f69c3-107">To add columns programmatically</span></span>  
  
1.  <span data-ttu-id="f69c3-108">Задайте в качестве <xref:System.Windows.Forms.ListView.View%2A> свойства <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="f69c3-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="f69c3-109">Используйте <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> метода в представлении списка <xref:System.Windows.Forms.ListView.Columns%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f69c3-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="f69c3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f69c3-110">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 [<span data-ttu-id="f69c3-111">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="f69c3-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="f69c3-112">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="f69c3-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
