---
title: Диалоговые окна в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
ms.openlocfilehash: ef07c087ca43efaf99231453fcb56af0db24234a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864259"
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="2cdef-102">Диалоговые окна в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cdef-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="2cdef-103">Диалоговые окна используются для взаимодействия с пользователем и получения информации.</span><span class="sxs-lookup"><span data-stu-id="2cdef-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="2cdef-104">Проще говоря, диалоговое окно представляет собой форму со значением ее свойства перечисления <xref:System.Windows.Forms.FormBorderStyle>, установленным в `FixedDialog`.</span><span class="sxs-lookup"><span data-stu-id="2cdef-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="2cdef-105">Можно создать собственные пользовательские диалоговые окна с помощью конструктора Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2cdef-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="2cdef-106">Для настройки диалоговых окон под конкретные потребности можно добавить элементы управления, такие как `Label`, `Textbox` и `Button`.</span><span class="sxs-lookup"><span data-stu-id="2cdef-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="2cdef-107">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Также включает стандартные диалоговые окна, такие как **Открытие файла** и окна сообщений, которые можно адаптировать для собственных приложений.</span><span class="sxs-lookup"><span data-stu-id="2cdef-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="2cdef-108">Дополнительные сведения см. в разделе [диалоговых элементов управления и компонентов](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="2cdef-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cdef-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2cdef-109">In This Section</span></span>  
 [<span data-ttu-id="2cdef-110">Практическое руководство. Отображение диалоговых окон для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cdef-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="2cdef-111">Указания по отображению диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="2cdef-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="2cdef-112">[Практическое: получение сведений из диалогового окна выборочно с помощью нескольких свойств](https://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](https://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="2cdef-113">[Практическое: получать сведения из родительской формы диалогового окна](https://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](https://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="2cdef-114">[Ввод пользовательских данных в диалоговые окна](https://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-114">[User Input to Dialog Boxes](https://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="2cdef-115">[Практическое: извлечение результата из диалоговых окон](https://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-115">[How to: Retrieve the Result for Dialog Boxes](https://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="2cdef-116">[Пошаговое руководство: Извлечение сведений из диалогового окна совместно с помощью объектов](https://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](https://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="2cdef-117">[Практическое: закройте диалоговые окна и сохранение введенных пользователем данных](https://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-117">[How to: Close Dialog Boxes and Retain User Input](https://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="2cdef-118">[Практическое: создание диалоговых окон во время разработки](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-118">[How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="2cdef-119">[Практическое: отображение окон сообщений](https://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="2cdef-119">[How to: Display Message Boxes](https://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2cdef-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2cdef-120">Related Sections</span></span>  
 [<span data-ttu-id="2cdef-121">Элементы управления и компоненты диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="2cdef-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="2cdef-122">Список стандартных элементов управления диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="2cdef-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="2cdef-123">Изменение внешнего вида Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2cdef-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="2cdef-124">Содержит ссылки на разделы, описывающие, как изменить внешний вид приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2cdef-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="2cdef-125">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="2cdef-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="2cdef-126">Объясняется, как включить элемент управления "Вкладка" в диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="2cdef-126">Explains how you incorporate the tab control into a dialog box.</span></span>
