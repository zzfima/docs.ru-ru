---
title: Общие сведения о компоненте управления NotifyIcon
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: 587bf514db853f1122ed16abc05a195985c5ce8d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742123"
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="0ef3f-102">Общие сведения о компоненте NotifyIcon (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-102">NotifyIcon Component Overview (Windows Forms)</span></span>

<span data-ttu-id="0ef3f-103">Компонент <xref:System.Windows.Forms.NotifyIcon> Windows Forms обычно используется для отображения значков процессов, выполняемых в фоновом режиме и большую часть времени не выводящих пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="0ef3f-104">Примером такого процесса является антивирусная программа, доступ к которой можно получить, щелкнув значок в области уведомлений о состоянии на панели задач.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>

## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="0ef3f-105">Основные свойства компонентов NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="0ef3f-105">Key Properties of NotifyIcons</span></span>

<span data-ttu-id="0ef3f-106">Каждый компонент <xref:System.Windows.Forms.NotifyIcon> выводит один значок в области состояния.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="0ef3f-107">Если для каждого из трех процессов, выполняемых в фоновом режиме, нужно показывать значок, добавьте три компонента <xref:System.Windows.Forms.NotifyIcon> в форму.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="0ef3f-108">Основные свойства компонента <xref:System.Windows.Forms.NotifyIcon> — это <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="0ef3f-109">Свойство <xref:System.Windows.Forms.NotifyIcon.Icon%2A> определяет значок, отображающийся в области состояния.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="0ef3f-110">Чтобы значок отображался, необходимо присвоить свойству <xref:System.Windows.Forms.NotifyIcon.Visible%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>

## <a name="notifyicons-options"></a><span data-ttu-id="0ef3f-111">Параметры компонентов NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="0ef3f-111">NotifyIcons Options</span></span>

<span data-ttu-id="0ef3f-112">Для упрощения работы пользователя можно связать всплывающие подсказки, сообщения и контекстные меню с <xref:System.Windows.Forms.NotifyIcon>.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-112">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>

<span data-ttu-id="0ef3f-113">Чтобы показать всплывающую подсказку для <xref:System.Windows.Forms.NotifyIcon>, вызовите метод <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A>, указав длительность отображения подсказки.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-113">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="0ef3f-114">Также можно указать текст, значок и заголовок подсказки с помощью свойств <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> и <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A> соответственно.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-114">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="0ef3f-115">Компоненты <xref:System.Windows.Forms.NotifyIcon> также могут иметь связанные всплывающие подсказки и контекстные меню.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-115"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="0ef3f-116">Дополнительные сведения см. в разделе [Общие сведения о компоненте ToolTip](tooltip-component-overview-windows-forms.md) и [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0ef3f-116">For more information, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ef3f-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0ef3f-117">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- [<span data-ttu-id="0ef3f-118">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="0ef3f-118">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
