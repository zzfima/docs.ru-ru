---
title: "Класс SoundPlayer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SoundPlayer
helpviewer_keywords: sounds [Windows Forms], playing
ms.assetid: f3945af9-045c-4e2d-b251-377c37ca2d77
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6fccf64215c38a3aee0b367866dd2371b483b0a7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="soundplayer-class"></a><span data-ttu-id="e8d89-102">Класс SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="e8d89-102">SoundPlayer Class</span></span>
<span data-ttu-id="e8d89-103">Класс `SoundPlayer` позволяет облегчить добавление звуков в приложениях.</span><span class="sxs-lookup"><span data-stu-id="e8d89-103">The `SoundPlayer` class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="e8d89-104">Можно также использовать класс <xref:System.Media.SystemSounds> для воспроизведения системных звуков, в том числе звукового сигнала.</span><span class="sxs-lookup"><span data-stu-id="e8d89-104">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8d89-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="e8d89-105">In This Section</span></span>  
 [<span data-ttu-id="e8d89-106">Общие сведения о классе SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="e8d89-106">SoundPlayer Class Overview</span></span>](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)  
 <span data-ttu-id="e8d89-107">Представляет класс и описывает его часто используемые свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="e8d89-107">Introduces the class and its commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="e8d89-108">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-108">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 <span data-ttu-id="e8d89-109">Приводится код для воспроизведения звука, указанного с помощью пути к файлу, пути UNC или HTTP.</span><span class="sxs-lookup"><span data-stu-id="e8d89-109">Provides code to play a sound specified via a file path, UNC path, or HTTP path.</span></span>  
  
 [<span data-ttu-id="e8d89-110">Практическое руководство. Подача звукового сигнала в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-110">How to: Play a Beep from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)  
 <span data-ttu-id="e8d89-111">Приводится код для воспроизведения звукового сигнала.</span><span class="sxs-lookup"><span data-stu-id="e8d89-111">Provides code to play the computer's beep sound.</span></span>  
  
 [<span data-ttu-id="e8d89-112">Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-112">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form.md)  
 <span data-ttu-id="e8d89-113">Приводится код для воспроизведения звука из ресурса.</span><span class="sxs-lookup"><span data-stu-id="e8d89-113">Provides code to play a sound from a resource.</span></span>  
  
 [<span data-ttu-id="e8d89-114">Практическое руководство. Воспроизведение системных звуков в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-114">How to: Play a System Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 <span data-ttu-id="e8d89-115">Приводится код для воспроизведения одного из системных звуков.</span><span class="sxs-lookup"><span data-stu-id="e8d89-115">Provides code to play the one of the system sounds.</span></span>  
  
 [<span data-ttu-id="e8d89-116">Практическое руководство. Асинхронная загрузка звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-116">How to: Load a Sound Asynchronously within a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)  
 <span data-ttu-id="e8d89-117">Приводится код для асинхронной загрузки звука по URL-адресу и его воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="e8d89-117">Provides code to load a sound asynchronously from a URL and play it.</span></span>  
  
 [<span data-ttu-id="e8d89-118">Практическое руководство. Циклическое воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-118">How to: Loop a Sound Playing on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)  
 <span data-ttu-id="e8d89-119">Приводится код для повторного воспроизведения звука.</span><span class="sxs-lookup"><span data-stu-id="e8d89-119">Provides code that plays a sound repeatedly.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e8d89-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="e8d89-120">Reference</span></span>  
 <xref:System.Media.SoundPlayer>  
 <span data-ttu-id="e8d89-121">Описание класса и ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="e8d89-121">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e8d89-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e8d89-122">Related Sections</span></span>  
 [<span data-ttu-id="e8d89-123">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-123">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="e8d89-124">Ссылки на разделы, посвященные элементам управления, которые предназначены специально для работы с Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e8d89-124">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="e8d89-125">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8d89-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="e8d89-126">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="e8d89-126">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 <span data-ttu-id="e8d89-127">См. также [гиперссылка «http://msdn.microsoft.com/library/11bxex12 (v=vs.110)» объект My.Computer](http://msdn.microsoft.com/library/11bxex12\(v=vs.110\)) или [объект My.Computer](http://msdn.microsoft.com/library/11bxex12\(v=vs.120\)).</span><span class="sxs-lookup"><span data-stu-id="e8d89-127">Also see [HYPERLINK "http://msdn.microsoft.com/library/11bxex12(v=vs.110)" My.Computer Object](http://msdn.microsoft.com/library/11bxex12\(v=vs.110\)) or [My.Computer Object](http://msdn.microsoft.com/library/11bxex12\(v=vs.120\)).</span></span>
