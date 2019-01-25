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
# <a name="soundplayer-class-overview"></a>Общие сведения о классе SoundPlayer
Класс <xref:System.Media.SoundPlayer> позволяет облегчить добавление звуков в приложениях.  
  
 <xref:System.Media.SoundPlayer> Класс может воспроизводить звуковые файлы в формате WAV из ресурса или расположения UNC или HTTP. Кроме того <xref:System.Media.SoundPlayer> класс позволяет загружать и воспроизводить звуки асинхронно.  
  
 Можно также использовать класс <xref:System.Media.SystemSounds> для воспроизведения системных звуков, в том числе звукового сигнала.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
  
|name|Описание:|  
|----------|-----------------|  
|Свойство <xref:System.Media.SoundPlayer.SoundLocation%2A>|Путь к файлу или веб-адресу звука. Допустимые значения включают UNC- или HTTP-путь.|  
|Свойство <xref:System.Media.SoundPlayer.LoadTimeout%2A>|Время ожидания программой загрузки звука (в миллисекундах), прежде чем будет создано исключение. По умолчанию используется значение 10 секунд.|  
|Свойство <xref:System.Media.SoundPlayer.IsLoadCompleted%2A>|Логическое значение, показывающее, завершилась ли загрузка звука.|  
|Метод <xref:System.Media.SoundPlayer.Load%2A>|Загружает звук синхронно.|  
|Метод <xref:System.Media.SoundPlayer.LoadAsync%2A>|Начинает загрузку звука асинхронно. Когда загрузка завершена, он вызывает <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> событий.|  
|Метод <xref:System.Media.SoundPlayer.Play%2A>|Воспроизводит звук, указанный в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойство в новом потоке.|  
|Метод <xref:System.Media.SoundPlayer.PlaySync%2A>|Воспроизводит звук, указанный в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойств в текущем потоке.|  
|Метод <xref:System.Media.SoundPlayer.Stop%2A>|Останавливает воспроизведение звука.|  
|Событие<xref:System.Media.SoundPlayer.LoadCompleted> |Возникает после попытки загрузки звука.|  
  
## <a name="see-also"></a>См. также
- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
