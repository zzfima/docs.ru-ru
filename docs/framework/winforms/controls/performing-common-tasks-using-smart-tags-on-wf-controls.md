---
title: "Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2e6b815be85576f037e0f24668c44756b95abd6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="1f1df-102">Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f1df-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="1f1df-103">При разработке форм и элементов управления для приложения Windows Forms, существует много задач, которые выполняются несколько раз.</span><span class="sxs-lookup"><span data-stu-id="1f1df-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="1f1df-104">Ниже приведено несколько наиболее типичных задач, которые указываются:</span><span class="sxs-lookup"><span data-stu-id="1f1df-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="1f1df-105">Добавление или удаление вкладки <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1f1df-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="1f1df-106">Закрепление элемента управления своему родителю.</span><span class="sxs-lookup"><span data-stu-id="1f1df-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="1f1df-107">Изменение ориентации элемента <xref:System.Windows.Forms.SplitContainer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1f1df-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="1f1df-108">Для ускорения разработки, многие элементы управления обладают смарт-тегов, которые находятся в контекстных меню, которые позволяют выполнять общие задачи, такие как их в одном жест во время разработки.</span><span class="sxs-lookup"><span data-stu-id="1f1df-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="1f1df-109">Эти задачи называются *командами смарт тегов*.</span><span class="sxs-lookup"><span data-stu-id="1f1df-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="1f1df-110">Смарт-теги остаются прикрепленными к экземпляру элемента управления для существования в конструкторе и всегда доступны.</span><span class="sxs-lookup"><span data-stu-id="1f1df-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="1f1df-111">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="1f1df-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="1f1df-112">Создание проекта Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f1df-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="1f1df-113">С помощью смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="1f1df-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="1f1df-114">Включение и отключение смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="1f1df-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="1f1df-115">После завершения вы будете понимать роль, которую играют эти важные функции макета.</span><span class="sxs-lookup"><span data-stu-id="1f1df-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f1df-116">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="1f1df-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1f1df-117">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="1f1df-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1f1df-118">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="1f1df-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="1f1df-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="1f1df-119">Creating the Project</span></span>  
 <span data-ttu-id="1f1df-120">Первым шагом является создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="1f1df-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="1f1df-121">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="1f1df-121">To create the project</span></span>  
  
1.  <span data-ttu-id="1f1df-122">Создайте проект приложения Windows с названием «SmartTagsExample».</span><span class="sxs-lookup"><span data-stu-id="1f1df-122">Create a Windows-based application project called "SmartTagsExample".</span></span> <span data-ttu-id="1f1df-123">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="1f1df-123">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="1f1df-124">Выберите форму в **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="1f1df-124">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="1f1df-125">С помощью смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="1f1df-125">Using Smart Tags</span></span>  
 <span data-ttu-id="1f1df-126">Смарт-теги всегда доступны во время разработки для элементов управления, которые их содержат.</span><span class="sxs-lookup"><span data-stu-id="1f1df-126">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="1f1df-127">Использование смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="1f1df-127">To use smart tags</span></span>  
  
1.  <span data-ttu-id="1f1df-128">Перетащите <xref:System.Windows.Forms.TabControl> из **элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="1f1df-128">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="1f1df-129">Обратите внимание, глиф смарт тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), которая отображается на краю <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1f1df-129">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="1f1df-130">Щелкните глиф смарт тега.</span><span class="sxs-lookup"><span data-stu-id="1f1df-130">Click the smart-tag glyph.</span></span> <span data-ttu-id="1f1df-131">Выберите в контекстном меню рядом с глифом, **добавить вкладку** элемента.</span><span class="sxs-lookup"><span data-stu-id="1f1df-131">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="1f1df-132">Обратите внимание, что добавляется новую страницу вкладки <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1f1df-132">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="1f1df-133">Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="1f1df-133">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="1f1df-134">Щелкните глиф смарт тега.</span><span class="sxs-lookup"><span data-stu-id="1f1df-134">Click the smart-tag glyph.</span></span> <span data-ttu-id="1f1df-135">Выберите в контекстном меню рядом с глифом, **добавить столбец** элемента.</span><span class="sxs-lookup"><span data-stu-id="1f1df-135">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="1f1df-136">Обратите внимание, что новый столбец будет добавлен <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1f1df-136">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="1f1df-137">Перетащите <xref:System.Windows.Forms.SplitContainer> управления из **элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="1f1df-137">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="1f1df-138">Щелкните глиф смарт тега.</span><span class="sxs-lookup"><span data-stu-id="1f1df-138">Click the smart-tag glyph.</span></span> <span data-ttu-id="1f1df-139">Выберите в контекстном меню рядом с глифом, **Ориентация горизонтального разделителя** элемента.</span><span class="sxs-lookup"><span data-stu-id="1f1df-139">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="1f1df-140">Обратите внимание, что <xref:System.Windows.Forms.SplitContainer> элемента управления разделителя — теперь имеет горизонтальную ориентацию.</span><span class="sxs-lookup"><span data-stu-id="1f1df-140">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f1df-141">См. также</span><span class="sxs-lookup"><span data-stu-id="1f1df-141">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [<span data-ttu-id="1f1df-142">Пошаговое руководство: Добавление смарт-тегов в компонент Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f1df-142">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
