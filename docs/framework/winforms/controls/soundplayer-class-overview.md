---
title: Общие сведения о классе SoundPlayer
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 041e7d0170bc98797278e209fd86cff0f82db9fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690696"
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="8528d-102">Общие сведения о классе SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="8528d-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="8528d-103">Класс <xref:System.Media.SoundPlayer> позволяет облегчить добавление звуков в приложениях.</span><span class="sxs-lookup"><span data-stu-id="8528d-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="8528d-104"><xref:System.Media.SoundPlayer> Класс может воспроизводить звуковые файлы в формате WAV из ресурса или расположения UNC или HTTP.</span><span class="sxs-lookup"><span data-stu-id="8528d-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="8528d-105">Кроме того <xref:System.Media.SoundPlayer> класс позволяет загружать и воспроизводить звуки асинхронно.</span><span class="sxs-lookup"><span data-stu-id="8528d-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="8528d-106">Можно также использовать класс <xref:System.Media.SystemSounds> для воспроизведения системных звуков, в том числе звукового сигнала.</span><span class="sxs-lookup"><span data-stu-id="8528d-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="8528d-107">Часто используемые свойства, методы и события</span><span class="sxs-lookup"><span data-stu-id="8528d-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="8528d-108">name</span><span class="sxs-lookup"><span data-stu-id="8528d-108">Name</span></span>|<span data-ttu-id="8528d-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="8528d-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8528d-110">Свойство <xref:System.Media.SoundPlayer.SoundLocation%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="8528d-111">Путь к файлу или веб-адресу звука.</span><span class="sxs-lookup"><span data-stu-id="8528d-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="8528d-112">Допустимые значения включают UNC- или HTTP-путь.</span><span class="sxs-lookup"><span data-stu-id="8528d-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="8528d-113">Свойство <xref:System.Media.SoundPlayer.LoadTimeout%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="8528d-114">Время ожидания программой загрузки звука (в миллисекундах), прежде чем будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="8528d-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="8528d-115">По умолчанию используется значение 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="8528d-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="8528d-116">Свойство <xref:System.Media.SoundPlayer.IsLoadCompleted%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="8528d-117">Логическое значение, показывающее, завершилась ли загрузка звука.</span><span class="sxs-lookup"><span data-stu-id="8528d-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="8528d-118">Метод <xref:System.Media.SoundPlayer.Load%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="8528d-119">Загружает звук синхронно.</span><span class="sxs-lookup"><span data-stu-id="8528d-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="8528d-120">Метод <xref:System.Media.SoundPlayer.LoadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="8528d-121">Начинает загрузку звука асинхронно.</span><span class="sxs-lookup"><span data-stu-id="8528d-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="8528d-122">Когда загрузка завершена, он вызывает <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> событий.</span><span class="sxs-lookup"><span data-stu-id="8528d-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="8528d-123">Метод <xref:System.Media.SoundPlayer.Play%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="8528d-124">Воспроизводит звук, указанный в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойство в новом потоке.</span><span class="sxs-lookup"><span data-stu-id="8528d-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="8528d-125">Метод <xref:System.Media.SoundPlayer.PlaySync%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="8528d-126">Воспроизводит звук, указанный в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойств в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="8528d-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="8528d-127">Метод <xref:System.Media.SoundPlayer.Stop%2A></span><span class="sxs-lookup"><span data-stu-id="8528d-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="8528d-128">Останавливает воспроизведение звука.</span><span class="sxs-lookup"><span data-stu-id="8528d-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="8528d-129">Событие<xref:System.Media.SoundPlayer.LoadCompleted> </span><span class="sxs-lookup"><span data-stu-id="8528d-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="8528d-130">Возникает после попытки загрузки звука.</span><span class="sxs-lookup"><span data-stu-id="8528d-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8528d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8528d-131">See also</span></span>
- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
