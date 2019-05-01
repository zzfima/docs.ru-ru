---
title: Элемент управления StatusBar (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
ms.openlocfilehash: 9ef6bc125a641538e7fd2da4c17c5f25dfc62709
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009660"
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="cfa9b-102">Элемент управления StatusBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cfa9b-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="cfa9b-103">Элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> заменяет элемент управления <xref:System.Windows.Forms.StatusBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.StatusBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="cfa9b-104">Элемент управления Windows Forms <xref:System.Windows.Forms.StatusBar> используется в формах в качестве области, обычно отображаемой в нижней части окна, в которой выводятся различные сведения о состоянии приложения.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="cfa9b-105"><xref:System.Windows.Forms.StatusBar> элементы управления могут иметь панели строки состояния, на которых выводятся значки, показывающие состояние, или набор значков в анимации, которые указывают, что процесс работает; например Microsoft Word, означает, что документ сохраняется.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfa9b-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="cfa9b-106">In This Section</span></span>  
 [<span data-ttu-id="cfa9b-107">Общие сведения об элементе управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="cfa9b-107">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="cfa9b-108">Основные понятия <xref:System.Windows.Forms.StatusBar> элемент управления, который позволяет пользователям видеть соответствующие сведения для элемента управления, имеющий фокус.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="cfa9b-109">Практическое руководство. Добавление панелей в элемент управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="cfa9b-109">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="cfa9b-110">Описание способов добавления программируемых панелей в <xref:System.Windows.Forms.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="cfa9b-111">Практическое руководство. Определить, какая из панелей в элемент управления Windows Forms StatusBar была нажата</span><span class="sxs-lookup"><span data-stu-id="cfa9b-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="cfa9b-112">Описание способов обработки <xref:System.Windows.Forms.Control.Click> события из <xref:System.Windows.Forms.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="cfa9b-113">Практическое руководство. Задать размер панели строки состояния</span><span class="sxs-lookup"><span data-stu-id="cfa9b-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="cfa9b-114">Подробные сведения о свойствах, которые управления шириной и изменение размеров панели строки состояния во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="cfa9b-115">Пошаговое руководство: Обновление строки состояния во время выполнения</span><span class="sxs-lookup"><span data-stu-id="cfa9b-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="cfa9b-116">Объясняется, как программно управлять данными в пределах панели строки состояния.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cfa9b-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="cfa9b-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="cfa9b-118">Справочная информация о классе и его членах.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="cfa9b-119">Заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cfa9b-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="cfa9b-120">Related Sections</span></span>  
 [<span data-ttu-id="cfa9b-121">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfa9b-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="cfa9b-122">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="cfa9b-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
