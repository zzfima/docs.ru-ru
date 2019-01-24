---
title: Как выполнить Задайте автоматическое слияние меню приложениях MDI
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 3aeaf9ee4818b6689905c10d2bd46fc887609c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549828"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="0d554-102">Как выполнить Задайте автоматическое слияние меню приложениях MDI</span><span class="sxs-lookup"><span data-stu-id="0d554-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="0d554-103">В следующей процедуре представлены основные шаги по настройке автоматического слияния в приложении многодокументного интерфейса (MDI) с <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="0d554-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="0d554-104">Чтобы задать автоматическое слияние меню</span><span class="sxs-lookup"><span data-stu-id="0d554-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="0d554-105">Создание родительской MDI-формы, задав его <xref:System.Windows.Forms.Form.IsMdiContainer%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="0d554-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="0d554-106">Добавить <xref:System.Windows.Forms.MenuStrip> для родительской формы MDI, установка его <xref:System.Windows.Forms.Form.MainMenuStrip%2A> свойства <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="0d554-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="0d554-107">Создание дочерних MDI-формы и задание его <xref:System.Windows.Forms.Form.MdiParent%2A> имя родительской формы.</span><span class="sxs-lookup"><span data-stu-id="0d554-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="0d554-108">Добавление <xref:System.Windows.Forms.MenuStrip> для дочерней формы MDI.</span><span class="sxs-lookup"><span data-stu-id="0d554-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="0d554-109">На дочерней формы, задайте <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойство <xref:System.Windows.Forms.MenuStrip> для `false`.</span><span class="sxs-lookup"><span data-stu-id="0d554-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="0d554-110">Добавление элементов меню в форме дочерних <xref:System.Windows.Forms.MenuStrip> , которые необходимо объединить в родительской формы <xref:System.Windows.Forms.MenuStrip> при активации дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="0d554-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="0d554-111">Используйте <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> свойства в меню элементов в форме дочерних <xref:System.Windows.Forms.MenuStrip> для управления слиянием в родительской формы.</span><span class="sxs-lookup"><span data-stu-id="0d554-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d554-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0d554-112">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="0d554-113">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="0d554-113">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
