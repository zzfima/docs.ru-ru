---
title: "Практическое руководство. Изменение внешнего вида элемента управления DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="72cc2-102">Практическое руководство. Изменение внешнего вида элемента управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="72cc2-102">How to: Change the Appearance of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="72cc2-103">Можно изменить внешний вид <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления во время разработки путем задания свойств или во время выполнения путем обработки <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событий.</span><span class="sxs-lookup"><span data-stu-id="72cc2-103">You can change the appearance of a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time by setting properties or at run time by handling the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event.</span></span>  
  
 <span data-ttu-id="72cc2-104">Свойства, которые заданы во время разработки, при выборе области шаблона элемента управления будет повторяться для каждого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="72cc2-104">Properties that you set at design time when the item template section of the control is selected will be repeated for each <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> at run time.</span></span> <span data-ttu-id="72cc2-105">Связанные свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> сам элемент управления будет отображаться во время выполнения остается только если часть контейнера были выявлены (например, если <xref:System.Windows.Forms.Control.Padding%2A> задано большое значение).</span><span class="sxs-lookup"><span data-stu-id="72cc2-105">Appearance-related properties of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control itself will be visible at run time only if a part of the container is left uncovered (for example, if the <xref:System.Windows.Forms.Control.Padding%2A> property is set to a large value).</span></span>  
  
 <span data-ttu-id="72cc2-106">Во время выполнения внешнего свойства могут задаваться на основе от условий.</span><span class="sxs-lookup"><span data-stu-id="72cc2-106">At run time, appearance-related properties can be set based on conditions.</span></span> <span data-ttu-id="72cc2-107">Например в такие приложения, можно изменить цвет фона элемента предупреждать пользователей, когда элемент просрочен.</span><span class="sxs-lookup"><span data-stu-id="72cc2-107">For example, in a scheduling application, you might change the background color of an item to warn users when an item is past due.</span></span> <span data-ttu-id="72cc2-108">В <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> обработчик событий, если задать свойство в условном операторе например `If…Then`, необходимо также использовать `Else` предложение для указания внешнего вида, если условие не выполнено.</span><span class="sxs-lookup"><span data-stu-id="72cc2-108">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, if you set a property in a conditional statement such as `If…Then`, you must also use an `Else` clause to specify the appearance when the condition is not met.</span></span>  
  
### <a name="to-change-the-appearance-at-design-time"></a><span data-ttu-id="72cc2-109">Чтобы изменить внешний вид во время разработки</span><span class="sxs-lookup"><span data-stu-id="72cc2-109">To change the appearance at design time</span></span>  
  
1.  <span data-ttu-id="72cc2-110">В конструкторе Windows Forms выберите область шаблона (верхнем) из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="72cc2-110">In the Windows Forms Designer, select the item template (upper) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="72cc2-111">В окне «Свойства» выберите свойство и измените значение.</span><span class="sxs-lookup"><span data-stu-id="72cc2-111">In the Properties window, select a property and change the value.</span></span> <span data-ttu-id="72cc2-112">Включать общие свойства, определяющие внешний вид <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, и <xref:System.Windows.Forms.Control.ForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="72cc2-112">Common properties that affect appearance include <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, and <xref:System.Windows.Forms.Control.ForeColor%2A>.</span></span>  
  
### <a name="to-change-the-appearance-at-run-time"></a><span data-ttu-id="72cc2-113">Чтобы изменить внешний вид во время выполнения</span><span class="sxs-lookup"><span data-stu-id="72cc2-113">To change the appearance at run time</span></span>  
  
1.  <span data-ttu-id="72cc2-114">В редакторе кода в раскрывающемся списке выберите **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="72cc2-114">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
2.  <span data-ttu-id="72cc2-115">В <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> обработчика событий, добавьте код для задания свойств:</span><span class="sxs-lookup"><span data-stu-id="72cc2-115">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add code to set the properties:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="72cc2-116">Пример</span><span class="sxs-lookup"><span data-stu-id="72cc2-116">Example</span></span>  
 <span data-ttu-id="72cc2-117">Некоторые стандартные настройки для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления включают возможности отображения строк различными цветами и изменения цвета поля на основе условия.</span><span class="sxs-lookup"><span data-stu-id="72cc2-117">Some common customizations for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control include displaying the rows in alternating colors and changing the color of a field based on a condition.</span></span> <span data-ttu-id="72cc2-118">В следующем примере показано, как выполнять эти настройки.</span><span class="sxs-lookup"><span data-stu-id="72cc2-118">The following example shows how to perform these customizations.</span></span> <span data-ttu-id="72cc2-119">В этом примере предполагается, что <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления с привязкой к таблице Products базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="72cc2-119">This example assumes that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that is bound to the Products table in the Northwind database.</span></span>  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 <span data-ttu-id="72cc2-120">Обратите внимание, что для всех этих настроек необходимо предоставить код для задания свойств для обеих сторон условия.</span><span class="sxs-lookup"><span data-stu-id="72cc2-120">Note that for both of these customizations, you must provide code to set the properties for both sides of the condition.</span></span> <span data-ttu-id="72cc2-121">Если вы не укажете `Else` условие, во время выполнения могут возникнуть непредсказуемые результаты.</span><span class="sxs-lookup"><span data-stu-id="72cc2-121">If you do not specify the `Else` condition, you will see unexpected results at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72cc2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="72cc2-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [<span data-ttu-id="72cc2-123">Общие сведения об элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="72cc2-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="72cc2-124">Устранение неполадок при использовании элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="72cc2-124">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="72cc2-125">Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="72cc2-125">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="72cc2-126">Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="72cc2-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="72cc2-127">Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="72cc2-127">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
