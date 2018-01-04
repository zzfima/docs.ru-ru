---
title: "Общие сведения об элементе управления StatusStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d1eb698dbb9168bf5de6d3982e19e69d170ac0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="3c4c2-102">Общие сведения об элементе управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3c4c2-102">StatusStrip Control Overview</span></span>
<span data-ttu-id="3c4c2-103">Элемент управления <xref:System.Windows.Forms.StatusStrip> отображает сведения об объекте, который просматривается в <xref:System.Windows.Forms.Form>, компонентах объекта или информации о контексте, относящиеся к работе объекта внутри приложения.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="3c4c2-104">Как правило, элемент управления <xref:System.Windows.Forms.StatusStrip> состоит из объектов <xref:System.Windows.Forms.ToolStripStatusLabel>, каждый из которых отображает текст, значок, либо и текст и значок.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="3c4c2-105"><xref:System.Windows.Forms.StatusStrip> также могут содержать элементы управления <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton> и <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="3c4c2-106">По умолчанию в <xref:System.Windows.Forms.StatusStrip> панели отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="3c4c2-107">Чтобы добавить панели в <xref:System.Windows.Forms.StatusStrip>, используйте метод <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3c4c2-108">Существует расширенная поддержка обработки элементов <xref:System.Windows.Forms.StatusStrip> и общих команд в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="3c4c2-109">См. также [редактор коллекции элементов StatusStrip](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [диалоговое окно задач StatusStrip](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="3c4c2-109">Also see [StatusStrip Items Collection Editor](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [StatusStrip Tasks Dialog Box](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)).</span></span>  
  
 <span data-ttu-id="3c4c2-110">Хотя <xref:System.Windows.Forms.StatusStrip> заменяет и расширяет элемент управления <xref:System.Windows.Forms.StatusBar> предыдущих версий, <xref:System.Windows.Forms.StatusBar> сохраняется для обеспечения обратной совместимости и использования в будущем при его выборе.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="3c4c2-111">Важные члены StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3c4c2-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="3c4c2-112">Имя</span><span class="sxs-lookup"><span data-stu-id="3c4c2-112">Name</span></span>|<span data-ttu-id="3c4c2-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="3c4c2-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="3c4c2-114">Возвращает или задает значение, которое указывает, поддерживает ли <xref:System.Windows.Forms.StatusStrip> область переполнения.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="3c4c2-115">Возвращает или задает значение, которое указывает, растягивается ли элемент управления <xref:System.Windows.Forms.StatusStrip> во всю длину в своем контейнере <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="3c4c2-116">Важные сопутствующие классы StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3c4c2-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="3c4c2-117">Имя</span><span class="sxs-lookup"><span data-stu-id="3c4c2-117">Name</span></span>|<span data-ttu-id="3c4c2-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="3c4c2-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="3c4c2-119">Представляет панель элемента управления <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="3c4c2-120">Отображает связанный <xref:System.Windows.Forms.ToolStripDropDown>, из которого пользователь может выбрать единичный элемент.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="3c4c2-121">Представляет элемент управления, состоящий из двух частей, которые являются обычной кнопкой и раскрывающимся меню.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="3c4c2-122">Отображает состояние завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="3c4c2-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c4c2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3c4c2-123">See Also</span></span>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
