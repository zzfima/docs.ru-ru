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
ms.openlocfilehash: b6df44df3582ed806d338e2d4565c5c11f69ce21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="soundplayer-class-overview"></a>Общие сведения о классе SoundPlayer
Класс <xref:System.Media.SoundPlayer> позволяет облегчить добавление звуков в приложениях.  
  
 <xref:System.Media.SoundPlayer> Класса можно воспроизводить звуковые файлы в формате WAV, либо из ресурса расположениях UNC или HTTP. Кроме того <xref:System.Media.SoundPlayer> класс позволяет загрузить или воспроизведение звуков в асинхронном режиме.  
  
 Можно также использовать класс <xref:System.Media.SystemSounds> для воспроизведения системных звуков, в том числе звукового сигнала.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
  
|Имя|Описание|  
|----------|-----------------|  
|Свойство <xref:System.Media.SoundPlayer.SoundLocation%2A>|Путь к файлу или веб-адресу звука. Допустимые значения включают UNC- или HTTP-путь.|  
|Свойство <xref:System.Media.SoundPlayer.LoadTimeout%2A>|Время ожидания программой загрузки звука (в миллисекундах), прежде чем будет создано исключение. По умолчанию используется значение 10 секунд.|  
|Свойство <xref:System.Media.SoundPlayer.IsLoadCompleted%2A>|Логическое значение, показывающее, завершилась ли загрузка звука.|  
|Метод <xref:System.Media.SoundPlayer.Load%2A>|Загружает звук синхронно.|  
|Метод <xref:System.Media.SoundPlayer.LoadAsync%2A>|Начинает загрузку звука асинхронно. Когда загрузка завершена, он выдает <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> событий.|  
|Метод <xref:System.Media.SoundPlayer.Play%2A>|Воспроизведение звука, указанного в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойства в новом потоке.|  
|Метод <xref:System.Media.SoundPlayer.PlaySync%2A>|Воспроизведение звука, указанного в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойства в текущем потоке.|  
|Метод <xref:System.Media.SoundPlayer.Stop%2A>|Останавливает воспроизведение звука.|  
|Событие <xref:System.Media.SoundPlayer.LoadCompleted>|Возникает после попытки загрузки звука.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
