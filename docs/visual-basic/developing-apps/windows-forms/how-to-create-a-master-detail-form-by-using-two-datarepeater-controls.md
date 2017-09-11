---
title: "Практическое руководство: создание главные и подчиненные формы с помощью двух элементов управления DataRepeater (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 4ed0b1fa0e7fac96cef3bde61efac66681f2507b
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="d10b7-102">Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d10b7-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="d10b7-103">Можно отобразить связанные данные с помощью двух или более <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>элементы управления для создания главного и подчиненного.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d10b7-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="d10b7-104">Например, может потребоваться отобразить список клиентов в одном <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, когда пользователь выбирает клиента, отображается список заказов этого клиента в секунду <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d10b7-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="d10b7-105">Можно отобразить связанные данные, перетащив подчиненные элементы, которые совместно используют один и тот же узел главной таблицы из **источников данных** окна на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d10b7-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d10b7-106">Например, если имеется источник данных, который имеет таблицу Customers и связанную таблицу Orders, обе таблицы будут отображаться как узлы верхнего уровня в представлении дерева в **источников данных** окна.</span><span class="sxs-lookup"><span data-stu-id="d10b7-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="d10b7-107">Разверните узел Customers, чтобы просмотреть столбцы.</span><span class="sxs-lookup"><span data-stu-id="d10b7-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="d10b7-108">Обратите внимание, что последний столбец в списке является разворачиваемым узлом, который представляет таблицу Orders.</span><span class="sxs-lookup"><span data-stu-id="d10b7-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="d10b7-109">Этот узел представляет связанные заказы для клиента.</span><span class="sxs-lookup"><span data-stu-id="d10b7-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="d10b7-110">Для отображения связанных данных в двух элементах управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d10b7-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="d10b7-111">Перетащите два <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управляет из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d10b7-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="d10b7-112">Перетащите маркеры изменения размера и положения элементов управления их размера и положения side-by-side.</span><span class="sxs-lookup"><span data-stu-id="d10b7-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="d10b7-113">В меню **Данные** выберите команду **Показать источники данных**.</span><span class="sxs-lookup"><span data-stu-id="d10b7-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d10b7-114">Если **источников данных** окно пусто, добавьте в источник данных.</span><span class="sxs-lookup"><span data-stu-id="d10b7-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="d10b7-115">Дополнительные сведения см. в разделе [добавить новые источники данных](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d10b7-115">For more information, see [Add new data sources](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="d10b7-116">В **источников данных** окно, выберите узел верхнего уровня в главной таблице.</span><span class="sxs-lookup"><span data-stu-id="d10b7-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="d10b7-117">Измените тип переноса главной таблицы на сведения, выбрав **сведений** в раскрывающемся списке узла таблицы.</span><span class="sxs-lookup"><span data-stu-id="d10b7-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="d10b7-118">Перетащите узел главной таблицы в область шаблона элемента первого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d10b7-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="d10b7-119">Разверните узел главной таблицы и выберите дочерний узел для связанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="d10b7-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="d10b7-120">Измените тип переноса дочерней таблицы на сведения, выбрав **сведений** в раскрывающемся списке узла таблицы.</span><span class="sxs-lookup"><span data-stu-id="d10b7-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="d10b7-121">Выберите этот узел таблицы и перетащите его в область шаблона элемента второго <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d10b7-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10b7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d10b7-122">See Also</span></span>  
 <span data-ttu-id="d10b7-123"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="d10b7-123"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span></span>   
<span data-ttu-id="d10b7-124"> [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d10b7-124"> [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d10b7-125"> [Практическое руководство: отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d10b7-125"> [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d10b7-126"> [Практическое руководство: отображение связанных данных в приложении Windows Forms приложения](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd) </span><span class="sxs-lookup"><span data-stu-id="d10b7-126"> [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd) </span></span>  
<span data-ttu-id="d10b7-127"> [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d10b7-127"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="d10b7-128"> [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="d10b7-128"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
