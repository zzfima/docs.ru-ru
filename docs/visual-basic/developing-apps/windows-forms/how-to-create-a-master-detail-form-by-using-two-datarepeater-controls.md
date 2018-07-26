---
title: 'Практическое: создать форму «основной-подробности» с помощью двух элементов управления DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245545"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="bba53-102">Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="bba53-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="bba53-103">Можно отобразить связанные данные с помощью двух или более <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элементы управления для создания формы «основной/подробности».</span><span class="sxs-lookup"><span data-stu-id="bba53-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="bba53-104">Например, может потребоваться отобразить список клиентов в одном <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, когда пользователь выбирает клиента, отображается список заказов этого клиента в секунду <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="bba53-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="bba53-105">Можно отобразить связанные данные, перетащив подчиненные элементы, которые совместно используют один и тот же узел главную таблицу из **источников данных** окна на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bba53-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="bba53-106">К примеру, если у вас есть источник данных, который имеет таблицу Customers и связанную таблицу Orders, обе таблицы будут отображаться как узлы высшего уровня в представлении в виде дерева в **источников данных** окна.</span><span class="sxs-lookup"><span data-stu-id="bba53-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="bba53-107">Разверните узел Customers, таким образом, чтобы просмотреть столбцы.</span><span class="sxs-lookup"><span data-stu-id="bba53-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="bba53-108">Обратите внимание, что последний столбец в списке разворачиваемый узел, представляющий таблицу Orders.</span><span class="sxs-lookup"><span data-stu-id="bba53-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="bba53-109">Этот узел представляет связанные заказы для клиента.</span><span class="sxs-lookup"><span data-stu-id="bba53-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="bba53-110">Для отображения связанных данных в двух элементов управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="bba53-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="bba53-111">Перетащите два <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управляет из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bba53-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="bba53-112">Перетащите маркеры изменения размера и положения, чтобы элементы управления их размера и положения side-by-side.</span><span class="sxs-lookup"><span data-stu-id="bba53-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="bba53-113">В меню **Данные** выберите команду **Показать источники данных**.</span><span class="sxs-lookup"><span data-stu-id="bba53-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bba53-114">Если **источников данных** окно пуст, добавьте в источник данных.</span><span class="sxs-lookup"><span data-stu-id="bba53-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="bba53-115">Дополнительные сведения см. в разделе [Добавление новых источников данных](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="bba53-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="bba53-116">В **источников данных** окно, выберите узел верхнего уровня в главной таблице.</span><span class="sxs-lookup"><span data-stu-id="bba53-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="bba53-117">Измените тип удаления главной таблицы на сведения, нажав кнопку **сведения** в раскрывающемся списке в узле таблицы.</span><span class="sxs-lookup"><span data-stu-id="bba53-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="bba53-118">Перетащите узел главной таблицы в области шаблона элемента первого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bba53-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="bba53-119">Разверните узел главной таблицы и выберите узел сведений для связанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="bba53-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="bba53-120">Измените тип удаления таблицы сведений на сведения, нажав кнопку **сведения** в раскрывающемся списке в узле таблицы.</span><span class="sxs-lookup"><span data-stu-id="bba53-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="bba53-121">Выберите этот узел таблицы и перетащите его в область шаблона элемента второго <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bba53-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba53-122">См. также</span><span class="sxs-lookup"><span data-stu-id="bba53-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="bba53-123">Общие сведения об элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="bba53-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="bba53-124">Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="bba53-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="bba53-125">Практическое руководство. Отображение связанных данные в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bba53-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="bba53-126">Практическое руководство. Изменение внешнего вида элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="bba53-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="bba53-127">Устранение неполадок при использовании элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="bba53-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
