---
title: Выполнение стандартных задач с помощью действий конструктора в элементах управления
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634897"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a><span data-ttu-id="0556e-102">Пошаговое руководство. выполнение стандартных задач с помощью действий конструктора</span><span class="sxs-lookup"><span data-stu-id="0556e-102">Walkthrough: Perform common tasks using designer actions</span></span>

<span data-ttu-id="0556e-103">При создании форм и элементов управления для Windows Formsного приложения часто приходится выполнять множество задач.</span><span class="sxs-lookup"><span data-stu-id="0556e-103">As you construct forms and controls for your Windows Forms application, there are many tasks you'll perform repeatedly.</span></span> <span data-ttu-id="0556e-104">В следующем списке приведены некоторые из наиболее часто выполняемых задач:</span><span class="sxs-lookup"><span data-stu-id="0556e-104">The following list shows some of the commonly performed tasks you'll come across:</span></span>

- <span data-ttu-id="0556e-105">Добавление или удаление вкладки <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="0556e-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>
- <span data-ttu-id="0556e-106">Закрепление элемента управления в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="0556e-106">Docking a control to its parent.</span></span>
- <span data-ttu-id="0556e-107">Изменение ориентации элемента управления <xref:System.Windows.Forms.SplitContainer>.</span><span class="sxs-lookup"><span data-stu-id="0556e-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="0556e-108">Для ускорения разработки многие элементы управления предлагают действия конструктора, которые являются контекстно-зависимыми меню, которые позволяют выполнять типичные задачи, например, в одном жесте во время разработки.</span><span class="sxs-lookup"><span data-stu-id="0556e-108">To speed development, many controls offer designer actions, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="0556e-109">Эти задачи называются *командами действий конструктора*.</span><span class="sxs-lookup"><span data-stu-id="0556e-109">These tasks are called *designer actions verbs*.</span></span>

<span data-ttu-id="0556e-110">Действия конструктора остаются присоединенными к экземпляру элемента управления на время его существования в конструкторе и всегда доступны.</span><span class="sxs-lookup"><span data-stu-id="0556e-110">Designer actions remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="0556e-111">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="0556e-111">Create the project</span></span>

<span data-ttu-id="0556e-112">Первым шагом является создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="0556e-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="0556e-113">В Visual Studio создайте проект приложения на основе Windows с именем **десигнерактионсексампле**.</span><span class="sxs-lookup"><span data-stu-id="0556e-113">In Visual Studio, create a Windows-based application project called **DesignerActionsExample**.</span></span>

2. <span data-ttu-id="0556e-114">Выберите форму в **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="0556e-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-designer-actions"></a><span data-ttu-id="0556e-115">Использование действий конструктора</span><span class="sxs-lookup"><span data-stu-id="0556e-115">Use designer actions</span></span>

<span data-ttu-id="0556e-116">Действия конструктора всегда доступны во время разработки в элементах управления, которые их предлагают.</span><span class="sxs-lookup"><span data-stu-id="0556e-116">Designer actions are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="0556e-117">Перетащите <xref:System.Windows.Forms.TabControl> с **панели элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="0556e-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="0556e-118">Обратите внимание на глиф действий конструктора (![маленькая черная стрелка](./media/designer-actions-glyph.gif)), которая отображается на стороне <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="0556e-118">Note the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="0556e-119">Щелкните глиф действия конструктора.</span><span class="sxs-lookup"><span data-stu-id="0556e-119">Click the designer actions glyph.</span></span> <span data-ttu-id="0556e-120">В контекстном меню, расположенном рядом с глифом, выберите элемент **вкладка добавить** .</span><span class="sxs-lookup"><span data-stu-id="0556e-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="0556e-121">Обратите внимание, что новая страница вкладки добавляется в <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="0556e-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="0556e-122">Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="0556e-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="0556e-123">Щелкните глиф действия конструктора.</span><span class="sxs-lookup"><span data-stu-id="0556e-123">Click the designer actions glyph.</span></span> <span data-ttu-id="0556e-124">В контекстном меню рядом с глифом выберите элемент **Добавить столбец** .</span><span class="sxs-lookup"><span data-stu-id="0556e-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="0556e-125">Обратите внимание, что новый столбец добавляется к элементу управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="0556e-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="0556e-126">Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="0556e-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="0556e-127">Щелкните глиф действия конструктора.</span><span class="sxs-lookup"><span data-stu-id="0556e-127">Click the designer actions glyph.</span></span> <span data-ttu-id="0556e-128">В контекстном меню, расположенном рядом с глифом, выберите элемент **ориентация разделителя по горизонтали** .</span><span class="sxs-lookup"><span data-stu-id="0556e-128">In the shortcut menu that appears next to the glyph, select the **Horizontal Splitter Orientation** item.</span></span> <span data-ttu-id="0556e-129">Обратите внимание, что теперь Панель разделителя элемента управления <xref:System.Windows.Forms.SplitContainer> ориентирована горизонтально.</span><span class="sxs-lookup"><span data-stu-id="0556e-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="0556e-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0556e-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
