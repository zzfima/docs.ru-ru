---
title: "Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a97899d544dcc0d9f9ad59cbb34a01da76ef5fe5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="e7c44-102">Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e7c44-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="e7c44-103">При просмотре пользователями данных, отображаемых в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>, им порой требуется часто обращаться к одному столбцу или набору столбцов.</span><span class="sxs-lookup"><span data-stu-id="e7c44-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="e7c44-104">Например при просмотре таблицы сведений о пользователе, содержащей много столбцов, полезно для отображения имени клиента постоянно при прокручивании остальных столбцов за пределы видимой области.</span><span class="sxs-lookup"><span data-stu-id="e7c44-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="e7c44-105">Для этого необходимо закрепить столбцы в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="e7c44-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="e7c44-106">При закреплении столбца все столбцы слева от него (или справа для языков с направлением письма справа налево) также закрепляются.</span><span class="sxs-lookup"><span data-stu-id="e7c44-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="e7c44-107">Закрепленные столбцы остаются на месте в то время, как остальные столбцы можно прокручивать.</span><span class="sxs-lookup"><span data-stu-id="e7c44-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="e7c44-108">Если разрешено переупорядочивание столбцов, закрепленные столбцы рассматриваются как группа, отличная от группы незакрепленных столбцов.</span><span class="sxs-lookup"><span data-stu-id="e7c44-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="e7c44-109">Пользователи могут переставлять местами столбцы в каждой из групп, но не могут перемещать столбцы из одной группы в другую.</span><span class="sxs-lookup"><span data-stu-id="e7c44-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="e7c44-110">В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e7c44-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e7c44-111">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e7c44-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7c44-112">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="e7c44-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e7c44-113">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="e7c44-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e7c44-114">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="e7c44-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="e7c44-115">Закрепление столбца с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e7c44-115">To freeze a column using the designer</span></span>  
  
1.  <span data-ttu-id="e7c44-116">Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **Правка столбцов**.</span><span class="sxs-lookup"><span data-stu-id="e7c44-116">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="e7c44-117">Выберите столбец из **выбранные столбцы** списка.</span><span class="sxs-lookup"><span data-stu-id="e7c44-117">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="e7c44-118">В **свойства столбца** сетка, <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="e7c44-118">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7c44-119">Можно также закрепить столбец при его добавлении, выбрав **зафиксированных** поле **добавить столбец** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e7c44-119">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c44-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e7c44-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e7c44-121">Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e7c44-121">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="e7c44-122">Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e7c44-122">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="e7c44-123">Как: отображение текста справа налево в формах Windows Forms для глобализации</span><span class="sxs-lookup"><span data-stu-id="e7c44-123">How to: Display Right-to-Left Text in Windows Forms for Globalization</span></span>](http://msdn.microsoft.com/en-us/f0663385-2354-4c65-8676-706422283b14)  
 [<span data-ttu-id="e7c44-124">Как: Создание проекта приложения Windows</span><span class="sxs-lookup"><span data-stu-id="e7c44-124">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="e7c44-125">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7c44-125">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
