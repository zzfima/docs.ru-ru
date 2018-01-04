---
title: "Общие сведения о классе SoundPlayer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dc355fbe0d8262cb24779b99375d6075f758bbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="c26d9-102">Общие сведения о классе SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="c26d9-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="c26d9-103">Класс <xref:System.Media.SoundPlayer> позволяет облегчить добавление звуков в приложениях.</span><span class="sxs-lookup"><span data-stu-id="c26d9-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="c26d9-104"><xref:System.Media.SoundPlayer> Класса можно воспроизводить звуковые файлы в формате WAV, либо из ресурса расположениях UNC или HTTP.</span><span class="sxs-lookup"><span data-stu-id="c26d9-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="c26d9-105">Кроме того <xref:System.Media.SoundPlayer> класс позволяет загрузить или воспроизведение звуков в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="c26d9-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="c26d9-106">Можно также использовать класс <xref:System.Media.SystemSounds> для воспроизведения системных звуков, в том числе звукового сигнала.</span><span class="sxs-lookup"><span data-stu-id="c26d9-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="c26d9-107">Часто используемые свойства, методы и события</span><span class="sxs-lookup"><span data-stu-id="c26d9-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="c26d9-108">name</span><span class="sxs-lookup"><span data-stu-id="c26d9-108">Name</span></span>|<span data-ttu-id="c26d9-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c26d9-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="c26d9-110">Свойство <xref:System.Media.SoundPlayer.SoundLocation%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="c26d9-111">Путь к файлу или веб-адресу звука.</span><span class="sxs-lookup"><span data-stu-id="c26d9-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="c26d9-112">Допустимые значения включают UNC- или HTTP-путь.</span><span class="sxs-lookup"><span data-stu-id="c26d9-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="c26d9-113">Свойство <xref:System.Media.SoundPlayer.LoadTimeout%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="c26d9-114">Время ожидания программой загрузки звука (в миллисекундах), прежде чем будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="c26d9-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="c26d9-115">По умолчанию используется значение 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="c26d9-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="c26d9-116">Свойство <xref:System.Media.SoundPlayer.IsLoadCompleted%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="c26d9-117">Логическое значение, показывающее, завершилась ли загрузка звука.</span><span class="sxs-lookup"><span data-stu-id="c26d9-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="c26d9-118">Метод <xref:System.Media.SoundPlayer.Load%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="c26d9-119">Загружает звук синхронно.</span><span class="sxs-lookup"><span data-stu-id="c26d9-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="c26d9-120">Метод <xref:System.Media.SoundPlayer.LoadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="c26d9-121">Начинает загрузку звука асинхронно.</span><span class="sxs-lookup"><span data-stu-id="c26d9-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="c26d9-122">Когда загрузка завершена, он выдает <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> событий.</span><span class="sxs-lookup"><span data-stu-id="c26d9-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="c26d9-123">Метод <xref:System.Media.SoundPlayer.Play%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="c26d9-124">Воспроизведение звука, указанного в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойства в новом потоке.</span><span class="sxs-lookup"><span data-stu-id="c26d9-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="c26d9-125">Метод <xref:System.Media.SoundPlayer.PlaySync%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="c26d9-126">Воспроизведение звука, указанного в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойства в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="c26d9-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="c26d9-127">Метод <xref:System.Media.SoundPlayer.Stop%2A></span><span class="sxs-lookup"><span data-stu-id="c26d9-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="c26d9-128">Останавливает воспроизведение звука.</span><span class="sxs-lookup"><span data-stu-id="c26d9-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="c26d9-129">Событие <xref:System.Media.SoundPlayer.LoadCompleted></span><span class="sxs-lookup"><span data-stu-id="c26d9-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="c26d9-130">Возникает после попытки загрузки звука.</span><span class="sxs-lookup"><span data-stu-id="c26d9-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c26d9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c26d9-131">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
