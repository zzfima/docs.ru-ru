---
title: "Практическое руководство: отображение связанных данных в элементе управления DataRepeater (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
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
ms.openlocfilehash: 677c964ee9ebbad6ec712a29c8b9c8920aa7e7ec
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="ce815-102">Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ce815-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="ce815-103">Наиболее распространенное использование <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>является элемент управления для отображения связанных данных из базы данных или другого источника данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="ce815-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="ce815-104">Помимо связанные элементы управления, можно добавить другие элементы управления, такие как статическая метка или изображение, которое повторяется для каждого элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="ce815-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="ce815-105">Дополнительные сведения см. в разделе [Практическое руководство: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ce815-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="ce815-106">Можно также привязать к источнику данных во время выполнения, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>Свойства `True` и источника данных в назначение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>свойство.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A></span><span class="sxs-lookup"><span data-stu-id="ce815-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="ce815-107">В этом случае необходимо управлять всеми аспектами взаимодействия с источником данных.</span><span class="sxs-lookup"><span data-stu-id="ce815-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="ce815-108">Дополнительные сведения см. в разделе [виртуальный режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ce815-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="ce815-109">Чтобы создать DataRepeater с привязкой к данным</span><span class="sxs-lookup"><span data-stu-id="ce815-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="ce815-110">Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="ce815-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="ce815-111">Перетащите маркеры изменения размера и положения размер и положение этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ce815-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="ce815-112">Обратите внимание, что элемент управления имеет двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="ce815-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="ce815-113">Верхняя область — *шаблона элемента*; элементы управления, добавляемые в шаблон будет повторяться в каждом элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>элемента управления во время выполнения.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="ce815-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="ce815-114">Нижняя область является *просмотра*, в котором будут отображены элементы.</span><span class="sxs-lookup"><span data-stu-id="ce815-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="ce815-115">Можно также изменить размер и расположение элемента управления или шаблон элемента, изменив **размер** и **позиции** свойства в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="ce815-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="ce815-116">В меню **Данные** выберите команду **Показать источники данных**.</span><span class="sxs-lookup"><span data-stu-id="ce815-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce815-117">Если **источников данных** окно пусто, добавьте в источник данных.</span><span class="sxs-lookup"><span data-stu-id="ce815-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="ce815-118">Дополнительные сведения см. в разделе [добавить новые источники данных](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="ce815-118">For more information, see [Add new data sources](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="ce815-119">В **источников данных** окно, выберите узел верхнего уровня для таблицы, которая содержит данные, которые необходимо выполнить привязку.</span><span class="sxs-lookup"><span data-stu-id="ce815-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="ce815-120">Измените тип удаления таблицы `Details` , щелкнув `Details` в раскрывающемся списке узла таблицы.</span><span class="sxs-lookup"><span data-stu-id="ce815-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="ce815-121">Выберите узел таблицы и перетащите его в область шаблона элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="ce815-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="ce815-122">Можно указать, какие типы элементов управления отображаются для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="ce815-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="ce815-123">Дополнительные сведения см. в разделе [задать элемент управления, создаваемый при перетаскивании из окна источников данных](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span><span class="sxs-lookup"><span data-stu-id="ce815-123">For more information, see [Set the control to be created when dragging from the Data Sources window](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce815-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ce815-124">See Also</span></span>  
 <span data-ttu-id="ce815-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="ce815-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span></span>   
<span data-ttu-id="ce815-126"> [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ce815-126"> [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="ce815-127"> [Практическое руководство: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ce815-127"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="ce815-128"> [Практическое руководство: создание Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="ce815-128"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="ce815-129"> [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ce815-129"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="ce815-130"> [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="ce815-130"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
