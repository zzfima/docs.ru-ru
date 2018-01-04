---
title: "Практическое руководство. Автоматическое слияние меню в приложениях MDI"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14f9d956763685b5c03419515780ee2a6c3ede7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="b4f32-102">Практическое руководство. Автоматическое слияние меню в приложениях MDI</span><span class="sxs-lookup"><span data-stu-id="b4f32-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="b4f32-103">Ниже приведены основные шаги по настройке автоматического слияния в приложении многодокументного интерфейса (MDI) с <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b4f32-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="b4f32-104">Чтобы настроить автоматическое слияние меню</span><span class="sxs-lookup"><span data-stu-id="b4f32-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="b4f32-105">Создание родительской MDI-формы, установив его <xref:System.Windows.Forms.Form.IsMdiContainer%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="b4f32-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="b4f32-106">Добавить <xref:System.Windows.Forms.MenuStrip> для родительской формы MDI, установка его <xref:System.Windows.Forms.Form.MainMenuStrip%2A> свойства <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b4f32-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="b4f32-107">Создание дочерних MDI-формы и задание его <xref:System.Windows.Forms.Form.MdiParent%2A> на имя родительской формы.</span><span class="sxs-lookup"><span data-stu-id="b4f32-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="b4f32-108">Добавить <xref:System.Windows.Forms.MenuStrip> в дочерней форме MDI.</span><span class="sxs-lookup"><span data-stu-id="b4f32-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="b4f32-109">В дочерней форме задайте <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойство <xref:System.Windows.Forms.MenuStrip> для `false`.</span><span class="sxs-lookup"><span data-stu-id="b4f32-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="b4f32-110">Добавление пунктов меню дочерней формы <xref:System.Windows.Forms.MenuStrip> , которую требуется объединить в родительскую форму <xref:System.Windows.Forms.MenuStrip> при активации дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="b4f32-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="b4f32-111">Используйте <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> свойства в меню элементы в дочерней формы <xref:System.Windows.Forms.MenuStrip> для управления слиянием в родительской формы.</span><span class="sxs-lookup"><span data-stu-id="b4f32-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f32-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b4f32-112">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="b4f32-113">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="b4f32-113">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
