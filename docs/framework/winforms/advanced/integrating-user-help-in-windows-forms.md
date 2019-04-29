---
title: Интеграция справки пользователя в формы Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: 207ceeafa2ea06340310577c636deb5ea1977aae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942926"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="ecd98-102">Интеграция справки пользователя в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ecd98-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="ecd98-103">Аспект essential, но часто не уделяют должного внимания, создания приложений на основе Windows — справочной системы, так как это которой пользователи обращаются за помощью в путаницы.</span><span class="sxs-lookup"><span data-stu-id="ecd98-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="ecd98-104">Windows Forms поддерживает два различных типов поддержки, в каждом предоставляемые [компонент HelpProvider](../controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ecd98-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="ecd98-105">Первый направляет пользователя к файлу справки HTML или HTML Help 1. *x* или следующих версий.</span><span class="sxs-lookup"><span data-stu-id="ecd98-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="ecd98-106">Второй может отображать краткое «Что это такое» — введите Help для отдельных элементов управления; Это особенно полезно в диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="ecd98-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="ecd98-107">Оба типа справки можно использовать в той же форме.</span><span class="sxs-lookup"><span data-stu-id="ecd98-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="ecd98-108">Кроме того [компонент ToolTip](../controls/tooltip-component-windows-forms.md) может использоваться для предоставления отдельной справки для элементов управления в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ecd98-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ecd98-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ecd98-109">In This Section</span></span>  
 [<span data-ttu-id="ecd98-110">Практическое руководство. Предоставление справки в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="ecd98-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="ecd98-111">Содержит сведения об использовании `HelpProvider` компонента, чтобы связать элементы управления с файлами справочной системы.</span><span class="sxs-lookup"><span data-stu-id="ecd98-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="ecd98-112">Практическое руководство. Отображение всплывающей справки</span><span class="sxs-lookup"><span data-stu-id="ecd98-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="ecd98-113">Содержит сведения об использовании `HelpProvider` компонент для отображения всплывающей справки в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ecd98-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="ecd98-114">Отображение справки по элементам управления с помощью подсказок</span><span class="sxs-lookup"><span data-stu-id="ecd98-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="ecd98-115">Описывает использование `ToolTip` компонент для отображения справки для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ecd98-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ecd98-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ecd98-116">Related Sections</span></span>  
 [<span data-ttu-id="ecd98-117">Компонент HelpProvider</span><span class="sxs-lookup"><span data-stu-id="ecd98-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="ecd98-118">Основные сведения о `HelpProvider` компонента.</span><span class="sxs-lookup"><span data-stu-id="ecd98-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="ecd98-119">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="ecd98-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="ecd98-120">Основные сведения о `ToolTip` компонента.</span><span class="sxs-lookup"><span data-stu-id="ecd98-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="ecd98-121">Общие сведения о Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ecd98-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="ecd98-122">Основные сведения о Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ecd98-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="ecd98-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ecd98-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="ecd98-124">Предоставляет общие сведения о Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ecd98-124">Provides an overview of Windows Forms.</span></span>
