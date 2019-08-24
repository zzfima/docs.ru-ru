---
title: Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015761"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="c7f38-102">Пошаговое руководство. Выполнение стандартных задач с помощью смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="c7f38-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="c7f38-103">При создании форм и элементов управления для приложения Windows Forms существует множество задач, которые будут выполняться многократно.</span><span class="sxs-lookup"><span data-stu-id="c7f38-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="c7f38-104">Ниже приведены некоторые из типичных выполняемых задач.</span><span class="sxs-lookup"><span data-stu-id="c7f38-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="c7f38-105">Добавление или удаление вкладки в <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="c7f38-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="c7f38-106">Закрепление элемента управления в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="c7f38-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="c7f38-107">Изменение ориентации <xref:System.Windows.Forms.SplitContainer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7f38-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="c7f38-108">Для ускорения разработки многие элементы управления предлагают интеллектуальные теги, которые представляют собой контекстно-зависимые меню, позволяющие выполнять общие задачи, такие как, в одном жесте во время разработки.</span><span class="sxs-lookup"><span data-stu-id="c7f38-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="c7f38-109">Эти задачи называются *командами смарт-тегов*.</span><span class="sxs-lookup"><span data-stu-id="c7f38-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="c7f38-110">Смарт-теги остаются присоединенными к экземпляру элемента управления на время его существования в конструкторе и всегда доступны.</span><span class="sxs-lookup"><span data-stu-id="c7f38-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="c7f38-111">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="c7f38-111">Create the project</span></span>

<span data-ttu-id="c7f38-112">Первым шагом является создание проекта и настройка формы.</span><span class="sxs-lookup"><span data-stu-id="c7f38-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="c7f38-113">В Visual Studio создайте проект приложения на основе Windows с именем **смарттагсексампле**.</span><span class="sxs-lookup"><span data-stu-id="c7f38-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="c7f38-114">Выберите форму в **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="c7f38-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="c7f38-115">Использование смарт-тегов</span><span class="sxs-lookup"><span data-stu-id="c7f38-115">Use smart tags</span></span>

<span data-ttu-id="c7f38-116">Смарт-теги всегда доступны во время разработки в элементах управления, которые их предлагают.</span><span class="sxs-lookup"><span data-stu-id="c7f38-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="c7f38-117">Перетащите элемент <xref:System.Windows.Forms.TabControl> из **области элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="c7f38-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="c7f38-118">Обратите внимание на глиф![](./media/vs-winformsmttagglyph.gif)смарт-тега, который отображается <xref:System.Windows.Forms.TabControl>на стороне.</span><span class="sxs-lookup"><span data-stu-id="c7f38-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="c7f38-119">Щелкните глиф смарт-тега.</span><span class="sxs-lookup"><span data-stu-id="c7f38-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="c7f38-120">В контекстном меню, расположенном рядом с глифом, выберите элемент **вкладка добавить** .</span><span class="sxs-lookup"><span data-stu-id="c7f38-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="c7f38-121">Обратите внимание, что новая страница вкладки добавляется <xref:System.Windows.Forms.TabControl>в.</span><span class="sxs-lookup"><span data-stu-id="c7f38-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="c7f38-122">Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="c7f38-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="c7f38-123">Щелкните глиф смарт-тега.</span><span class="sxs-lookup"><span data-stu-id="c7f38-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="c7f38-124">В контекстном меню рядом с глифом выберите элемент **Добавить столбец** .</span><span class="sxs-lookup"><span data-stu-id="c7f38-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="c7f38-125">Обратите внимание, что к <xref:System.Windows.Forms.TableLayoutPanel> элементу управления добавляется новый столбец.</span><span class="sxs-lookup"><span data-stu-id="c7f38-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="c7f38-126">Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="c7f38-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="c7f38-127">Щелкните глиф смарт-тега.</span><span class="sxs-lookup"><span data-stu-id="c7f38-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="c7f38-128">В контекстном меню, расположенном рядом с глифом, выберите элемент **ориентация разделителя по горизонтали** .</span><span class="sxs-lookup"><span data-stu-id="c7f38-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="c7f38-129">Обратите внимание <xref:System.Windows.Forms.SplitContainer> , что теперь полоса разделения элемента управления ориентирована горизонтально.</span><span class="sxs-lookup"><span data-stu-id="c7f38-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7f38-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c7f38-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
