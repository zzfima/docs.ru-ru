---
title: Справка по интеграции пользователей
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: c402615d68c75327613d21bd35f1587b10f1dbf3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731576"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="25beb-102">Интеграция справки пользователя в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25beb-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="25beb-103">Важным, но часто с незнакомым аспектом создания приложений на основе Windows является справочная система, так как в этом случае пользователи могут не обращаться за помощью к времени путаницы.</span><span class="sxs-lookup"><span data-stu-id="25beb-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="25beb-104">Windows Forms поддерживают два разных типа справки, каждая из которых предоставляется [компонентом HelpProvider](../controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="25beb-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="25beb-105">Первый включает в себя указание пользователя на файл справки HTML или HTML Help 1. формат *x* или более.</span><span class="sxs-lookup"><span data-stu-id="25beb-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="25beb-106">Во втором может отображаться краткий обзор справки по типам отдельных элементов управления. Это особенно полезно в диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="25beb-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="25beb-107">Оба типа справки можно использовать в одной и той же форме.</span><span class="sxs-lookup"><span data-stu-id="25beb-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="25beb-108">Кроме того, [компонент ToolTip](../controls/tooltip-component-windows-forms.md) можно использовать для предоставления отдельной справки по элементам управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="25beb-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25beb-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="25beb-109">In This Section</span></span>  
 [<span data-ttu-id="25beb-110">Руководство: предоставление справки в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="25beb-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="25beb-111">Объясняет, как использовать компонент `HelpProvider` для связывания элементов управления с файлами в справочной системе.</span><span class="sxs-lookup"><span data-stu-id="25beb-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="25beb-112">Практическое руководство. Отображение всплывающей справки</span><span class="sxs-lookup"><span data-stu-id="25beb-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="25beb-113">Объясняется, как использовать компонент `HelpProvider` для отображения всплывающей справки по Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="25beb-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="25beb-114">Отображение справки по элементам управления с помощью подсказок</span><span class="sxs-lookup"><span data-stu-id="25beb-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="25beb-115">Описывает использование компонента `ToolTip` для отображения справки, относящейся к конкретному элементу управления.</span><span class="sxs-lookup"><span data-stu-id="25beb-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="25beb-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="25beb-116">Related Sections</span></span>  
 [<span data-ttu-id="25beb-117">Компонент HelpProvider</span><span class="sxs-lookup"><span data-stu-id="25beb-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="25beb-118">Основные сведения о компоненте `HelpProvider`.</span><span class="sxs-lookup"><span data-stu-id="25beb-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="25beb-119">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="25beb-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="25beb-120">Основные сведения о компоненте `ToolTip`.</span><span class="sxs-lookup"><span data-stu-id="25beb-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="25beb-121">Общие сведения о Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25beb-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="25beb-122">Основные сведения о Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="25beb-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="25beb-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25beb-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="25beb-124">Содержит общие сведения о Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="25beb-124">Provides an overview of Windows Forms.</span></span>
