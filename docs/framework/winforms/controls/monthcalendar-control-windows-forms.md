---
title: "Элемент управления MonthCalendar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- calendar controls
- MonthCalendar control [Windows Forms]
- dates [Windows Forms], controls
- calendars
ms.assetid: 051c6518-e0ca-426b-855c-f9bf70972970
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d4823b7d7411b7896e723683b70021292dd989aa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="monthcalendar-control-windows-forms"></a><span data-ttu-id="af89d-102">Элемент управления MonthCalendar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="af89d-102">MonthCalendar Control (Windows Forms)</span></span>
<span data-ttu-id="af89d-103">Windows Forms `MonthCalendar` управления предоставляет интуитивно понятный графический интерфейс для пользователей, для просмотра и задания сведений о дате.</span><span class="sxs-lookup"><span data-stu-id="af89d-103">The Windows Forms `MonthCalendar` control presents an intuitive graphical interface for users to view and set date information.</span></span> <span data-ttu-id="af89d-104">Элемент управления отображает сетку, содержащую пронумерованные дни месяца, разбитые на столбцы по дням недели.</span><span class="sxs-lookup"><span data-stu-id="af89d-104">The control displays a grid containing the numbered days of the month, arranged in columns underneath the days of the week.</span></span> <span data-ttu-id="af89d-105">С помощью кнопок со стрелками слева от заголовка месяца можно выбрать другой месяц.</span><span class="sxs-lookup"><span data-stu-id="af89d-105">You can select a different month by clicking the arrow buttons on either side of the month caption.</span></span> <span data-ttu-id="af89d-106">В отличие от аналогичного <xref:System.Windows.Forms.DateTimePicker> управления, можно выбрать диапазон дат с этим элементом управления; Однако <xref:System.Windows.Forms.DateTimePicker> позволяет задать время, а также даты.</span><span class="sxs-lookup"><span data-stu-id="af89d-106">Unlike the similar <xref:System.Windows.Forms.DateTimePicker> control, you can select a range of dates with this control; however, the <xref:System.Windows.Forms.DateTimePicker> control allows you to set times as well as dates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af89d-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="af89d-107">In This Section</span></span>  
 [<span data-ttu-id="af89d-108">Общие сведения об элементе управления MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="af89d-108">MonthCalendar Control Overview</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md)  
 <span data-ttu-id="af89d-109">Основные понятия `MonthCalendar` управления, который позволяет пользователям просматривать и задавать сведения о дате для приложения.</span><span class="sxs-lookup"><span data-stu-id="af89d-109">Introduces the general concepts of the `MonthCalendar` control, which allows users to view and set date information for an application.</span></span>  
  
 [<span data-ttu-id="af89d-110">Практическое руководство. Изменение внешнего вида элемента управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af89d-110">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 <span data-ttu-id="af89d-111">Описывает, как настроить внешний вид `MonthCalendar` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af89d-111">Describes how to customize the appearance of the `MonthCalendar` control.</span></span>  
  
 [<span data-ttu-id="af89d-112">Практическое руководство. Отображение более чем одного месяца в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af89d-112">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)  
 <span data-ttu-id="af89d-113">Описываются способы настройки `MonthCalendar` элемента управления для отображения нескольких месяцев одновременно.</span><span class="sxs-lookup"><span data-stu-id="af89d-113">Describes how to configure the `MonthCalendar` control to display several months simultaneously.</span></span>  
  
 [<span data-ttu-id="af89d-114">Практическое руководство. Отображение определенных дней полужирным шрифтом в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af89d-114">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 <span data-ttu-id="af89d-115">Описание для задания определенных дат отображаются полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="af89d-115">Explains how to set certain dates to appear bold.</span></span>  
  
 [<span data-ttu-id="af89d-116">Практическое руководство. Выбор диапазона дат в элементе управления MonthCalendar в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af89d-116">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 <span data-ttu-id="af89d-117">Объясняет, как программно выбрать диапазон дат из `MonthCalendar` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af89d-117">Explains how to programmatically select a range of dates from the `MonthCalendar` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="af89d-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="af89d-118">Reference</span></span>  
 <xref:System.Windows.Forms.MonthCalendar>  
 <span data-ttu-id="af89d-119">Справочная информация о классе и его членах.</span><span class="sxs-lookup"><span data-stu-id="af89d-119">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="af89d-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="af89d-120">Related Sections</span></span>  
 [<span data-ttu-id="af89d-121">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af89d-121">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="af89d-122">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="af89d-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="af89d-123">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="af89d-123">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 <span data-ttu-id="af89d-124">Описывает элемент управления, подобный <xref:System.Windows.Forms.MonthCalendar>, хотя <xref:System.Windows.Forms.DateTimePicker> управления также позволяет выбрать другое время и не позволяют выбрать диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="af89d-124">Describes a control similar to <xref:System.Windows.Forms.MonthCalendar>, although the <xref:System.Windows.Forms.DateTimePicker> control also allows you to select a time and does not allow you to select a range of dates.</span></span>
