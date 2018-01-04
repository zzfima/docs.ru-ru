---
title: "Интеграция справки пользователя в формы Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9563ce0ca95a728cc1a9aaa219fbc9fea2cd7153
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="c7985-102">Интеграция справки пользователя в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7985-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="c7985-103">Важным аспектом построения приложений Windows essential, но часто уделяется недостаточно внимания представлены справочной системы, где пользователи обращаются за помощью в недоразумений.</span><span class="sxs-lookup"><span data-stu-id="c7985-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="c7985-104">Windows Forms поддерживает два типа справки, в каждом предоставляемые [компонент HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c7985-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="c7985-105">Первый направляет пользователя на файл справки HTML или HTML Help 1. *x* или следующих версий.</span><span class="sxs-lookup"><span data-stu-id="c7985-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="c7985-106">Второй может отображать краткую «Что это такое» — введите Help для отдельных элементов управления; Это особенно удобно в диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="c7985-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="c7985-107">Оба типа справки можно использовать в той же форме.</span><span class="sxs-lookup"><span data-stu-id="c7985-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="c7985-108">Кроме того [компонент ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) может использоваться для предоставления отдельной справки для элементов управления в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c7985-108">Additionally, the [ToolTip Component](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7985-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c7985-109">In This Section</span></span>  
 [<span data-ttu-id="c7985-110">Руководство: предоставление справки в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="c7985-110">How to: Provide Help in a Windows Application</span></span>](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="c7985-111">Описание способов использования `HelpProvider` компонента, чтобы связать элементы управления с файлами справочной системы.</span><span class="sxs-lookup"><span data-stu-id="c7985-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="c7985-112">Практическое руководство. Отображение всплывающей справки</span><span class="sxs-lookup"><span data-stu-id="c7985-112">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 <span data-ttu-id="c7985-113">Описание способов использования `HelpProvider` компонент для отображения всплывающей справки в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c7985-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="c7985-114">Отображение справки по элементам управления с помощью подсказок</span><span class="sxs-lookup"><span data-stu-id="c7985-114">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 <span data-ttu-id="c7985-115">Описывает использование `ToolTip` компонент для отображения справки для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7985-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c7985-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c7985-116">Related Sections</span></span>  
 [<span data-ttu-id="c7985-117">Компонент HelpProvider</span><span class="sxs-lookup"><span data-stu-id="c7985-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="c7985-118">Основные сведения о `HelpProvider` компонента.</span><span class="sxs-lookup"><span data-stu-id="c7985-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="c7985-119">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="c7985-119">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="c7985-120">Основные сведения о `ToolTip` компонента.</span><span class="sxs-lookup"><span data-stu-id="c7985-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="c7985-121">Общие сведения о Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7985-121">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 <span data-ttu-id="c7985-122">Основные сведения о Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c7985-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="c7985-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7985-123">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)  
 <span data-ttu-id="c7985-124">Общие сведения о Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c7985-124">Provides an overview of Windows Forms.</span></span>
