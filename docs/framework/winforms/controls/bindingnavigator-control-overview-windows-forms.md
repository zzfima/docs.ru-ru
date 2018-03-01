---
title: "Общие сведения об элементе управления BindingNavigator (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 921f8c7791620d51107fa2ff31a637094fc0c633
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="bindingnavigator-control-overview-windows-forms"></a><span data-ttu-id="01d57-102">Общие сведения об элементе управления BindingNavigator (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="01d57-102">BindingNavigator Control Overview (Windows Forms)</span></span>
<span data-ttu-id="01d57-103">Элемент управления <xref:System.Windows.Forms.BindingNavigator> можно использовать для создания стандартных средств поиска и изменения данных в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="01d57-103">You can use the <xref:System.Windows.Forms.BindingNavigator> control to create a standardized means for users to search and change data on a Windows Form.</span></span> <span data-ttu-id="01d57-104">Элемент управления <xref:System.Windows.Forms.BindingNavigator> часто используется с компонентом <xref:System.Windows.Forms.BindingSource>, позволяя пользователям переходить по записям данных в форме и взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="01d57-104">You frequently use <xref:System.Windows.Forms.BindingNavigator> with the <xref:System.Windows.Forms.BindingSource> component to enable users to move through data records on a form and interact with the records.</span></span>  
  
## <a name="how-the-bindingnavigator-works"></a><span data-ttu-id="01d57-105">Как работает элемент управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="01d57-105">How the BindingNavigator Works</span></span>  
 <span data-ttu-id="01d57-106">Элемент управления <xref:System.Windows.Forms.BindingNavigator> состоит из элемента <xref:System.Windows.Forms.ToolStrip> с набором объектов <xref:System.Windows.Forms.ToolStripItem> для большинства обычных действий с данными: их добавления, удаления и перемещения по ним.</span><span class="sxs-lookup"><span data-stu-id="01d57-106">The <xref:System.Windows.Forms.BindingNavigator> control is composed of a <xref:System.Windows.Forms.ToolStrip> with a series of <xref:System.Windows.Forms.ToolStripItem> objects for most of the common data-related actions: adding data, deleting data, and navigating through data.</span></span> <span data-ttu-id="01d57-107">По умолчанию элемент управления <xref:System.Windows.Forms.BindingNavigator> содержит эти стандартные кнопки.</span><span class="sxs-lookup"><span data-stu-id="01d57-107">By default, the <xref:System.Windows.Forms.BindingNavigator> control contains these standard buttons.</span></span> <span data-ttu-id="01d57-108">На снимке экрана ниже показан элемент управления <xref:System.Windows.Forms.BindingNavigator>, размещенный на форме.</span><span class="sxs-lookup"><span data-stu-id="01d57-108">The following screen shot shows the <xref:System.Windows.Forms.BindingNavigator> control on a form.</span></span>  
  
 <span data-ttu-id="01d57-109">![Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "cpDataContainerCtrl")</span><span class="sxs-lookup"><span data-stu-id="01d57-109">![BindingNavigator Control](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "cpDataContainerCtrl")</span></span>  
  
 <span data-ttu-id="01d57-110">В таблице ниже перечислены элементы управления и их функции.</span><span class="sxs-lookup"><span data-stu-id="01d57-110">The following table lists the controls and describes their functions.</span></span>  
  
|<span data-ttu-id="01d57-111">Control</span><span class="sxs-lookup"><span data-stu-id="01d57-111">Control</span></span>|<span data-ttu-id="01d57-112">Функция</span><span class="sxs-lookup"><span data-stu-id="01d57-112">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="01d57-113">Кнопка <xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> </span><span class="sxs-lookup"><span data-stu-id="01d57-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> button</span></span>|<span data-ttu-id="01d57-114">Вставляет новую строку в базовый источник данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-114">Inserts a new row into the underlying data source.</span></span>|  
|<span data-ttu-id="01d57-115">Кнопка <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A></span><span class="sxs-lookup"><span data-stu-id="01d57-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button</span></span>|<span data-ttu-id="01d57-116">Удаляет текущую строку из базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-116">Deletes the current row from the underlying data source.</span></span>|  
|<span data-ttu-id="01d57-117">Кнопка <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A></span><span class="sxs-lookup"><span data-stu-id="01d57-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button</span></span>|<span data-ttu-id="01d57-118">Переход к первому элементу базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-118">Moves to the first item in the underlying data source.</span></span>|  
|<span data-ttu-id="01d57-119">Кнопка <xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> </span><span class="sxs-lookup"><span data-stu-id="01d57-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> button</span></span>|<span data-ttu-id="01d57-120">Переход к последнему элементу базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-120">Moves to the last item in the underlying data source.</span></span>|  
|<span data-ttu-id="01d57-121">Кнопка <xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A></span><span class="sxs-lookup"><span data-stu-id="01d57-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> button</span></span>|<span data-ttu-id="01d57-122">Переход к следующему элементу базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-122">Moves to the next item in the underlying data source.</span></span>|  
|<span data-ttu-id="01d57-123">Кнопка <xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A></span><span class="sxs-lookup"><span data-stu-id="01d57-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> button</span></span>|<span data-ttu-id="01d57-124">Переход к предыдущему элементу базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-124">Moves to the previous item in the underlying data source.</span></span>|  
|<span data-ttu-id="01d57-125">Текстовое поле <xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> </span><span class="sxs-lookup"><span data-stu-id="01d57-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> text box</span></span>|<span data-ttu-id="01d57-126">Возвращает текущую позицию в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-126">Returns the current position within the underlying data source.</span></span>|  
|<span data-ttu-id="01d57-127">Текстовое поле <xref:System.Windows.Forms.BindingNavigator.CountItem%2A></span><span class="sxs-lookup"><span data-stu-id="01d57-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> text box</span></span>|<span data-ttu-id="01d57-128">Возвращает общее число элементов в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="01d57-128">Returns the total number of items in the underlying data source.</span></span>|  
  
 <span data-ttu-id="01d57-129">Каждому элементу управления этой коллекции соответствует член компонента <xref:System.Windows.Forms.BindingSource>, обеспечивающий ту же функциональность программным путем.</span><span class="sxs-lookup"><span data-stu-id="01d57-129">For each control in this collection, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically provides the same functionality.</span></span> <span data-ttu-id="01d57-130">Например, кнопка <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> соответствует методу <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> компонента <xref:System.Windows.Forms.BindingSource>, кнопка <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> соответствует методу <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> и т. д.</span><span class="sxs-lookup"><span data-stu-id="01d57-130">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span>  
  
 <span data-ttu-id="01d57-131">Если кнопки по умолчанию не удовлетворяют требованиям приложения или необходимо использовать дополнительные кнопки с иной функциональностью, можно создать собственные кнопки <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="01d57-131">If the default buttons are not suited to your application, or if you require additional buttons to support other types of functionality, you can supply your own <xref:System.Windows.Forms.ToolStrip> buttons.</span></span> <span data-ttu-id="01d57-132">См. также [Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="01d57-132">Also see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d57-133">См. также</span><span class="sxs-lookup"><span data-stu-id="01d57-133">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="01d57-134">Элемент управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="01d57-134">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
