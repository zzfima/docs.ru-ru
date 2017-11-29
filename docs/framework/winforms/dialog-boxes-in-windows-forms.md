---
title: "Диалоговые окна в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1660bf08f10a7d4e0db4b7ae8d58fd631986974c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="89309-102">Диалоговые окна в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89309-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="89309-103">Диалоговые окна используются для взаимодействия с пользователем и получения информации.</span><span class="sxs-lookup"><span data-stu-id="89309-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="89309-104">Проще говоря, диалоговое окно представляет собой форму со значением ее свойства перечисления <xref:System.Windows.Forms.FormBorderStyle>, установленным в `FixedDialog`.</span><span class="sxs-lookup"><span data-stu-id="89309-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="89309-105">С помощью конструктора Windows Forms в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] вы можете создавать собственные пользовательские диалоговые окна.</span><span class="sxs-lookup"><span data-stu-id="89309-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="89309-106">Для настройки диалоговых окон под конкретные потребности можно добавить элементы управления, такие как `Label`, `Textbox` и `Button`.</span><span class="sxs-lookup"><span data-stu-id="89309-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="89309-107">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Также включает стандартные диалоговые окна, такие как **Открытие файла** и окна сообщений, которые можно использовать для собственных приложений.</span><span class="sxs-lookup"><span data-stu-id="89309-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="89309-108">Дополнительные сведения см. в разделе [диалогового окна элементы управления и компоненты](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="89309-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89309-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="89309-109">In This Section</span></span>  
 [<span data-ttu-id="89309-110">Практическое руководство. Отображение диалоговых окон для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89309-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="89309-111">Указания по отображению диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="89309-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="89309-112">[Как: получение сведений из диалогового окна выборочно с помощью нескольких свойств](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="89309-113">[Как: получение сведений из родительской формы диалогового окна](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="89309-114">[Ввод данных пользователем в диалоговые окна](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-114">[User Input to Dialog Boxes](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="89309-115">[Как: получить результат диалоговых окон](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-115">[How to: Retrieve the Result for Dialog Boxes](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="89309-116">[Пошаговое руководство: Извлечение сведений из диалогового окна совместно с помощью объектов](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="89309-117">[Как: закройте диалоговые окна и сохранить ввод данных пользователем](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-117">[How to: Close Dialog Boxes and Retain User Input](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="89309-118">[Как: создание диалоговые окна во время разработки](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-118">[How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="89309-119">[Как: отображения окон сообщений](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="89309-119">[How to: Display Message Boxes](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="89309-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="89309-120">Related Sections</span></span>  
 [<span data-ttu-id="89309-121">Элементы управления и компоненты диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="89309-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="89309-122">Список стандартных элементов управления диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="89309-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="89309-123">Изменение внешнего вида Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89309-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="89309-124">Содержит ссылки на разделы, описывающие, как изменить внешний вид приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="89309-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="89309-125">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="89309-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="89309-126">Объясняется, как включить элемент управления "Вкладка" в диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="89309-126">Explains how you incorporate the tab control into a dialog box.</span></span>
