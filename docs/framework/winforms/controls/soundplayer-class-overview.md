---
title: "Общие сведения о классе SoundPlayer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "воспроизведение звуков, класс SoundPlayer"
  - "Класс SoundPlayer, сведения о классе SoundPlayer"
  - "воспроизведение звуков"
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения о классе SoundPlayer
<xref:System.Media.SoundPlayer> позволяет облегчить добавление звуков в приложениях.  
  
 <xref:System.Media.SoundPlayer> класса можно воспроизводить звуковые файлы в формате WAV, либо из ресурса расположения UNC или HTTP. Кроме того <xref:System.Media.SoundPlayer> класс позволяет загружать и воспроизводить звуки асинхронно.  
  
 Можно также использовать <xref:System.Media.SystemSounds> класса для воспроизведения системных звуков, в том числе звукового сигнала.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
  
|Имя|Описание|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> свойство|Путь к файлу или веб-адрес звука. Допустимые значения могут быть UNC или HTTP.|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> свойство|Количество миллисекунд ожидания программы для загрузки звука, прежде чем он создает исключение. По умолчанию используется значение 10 секунд.|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> свойство|Логическое значение, указывающее, завершено ли загрузка звука.|  
|<xref:System.Media.SoundPlayer.Load%2A> метод|Синхронно загружает звуковой файл.|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> метод|Начинает асинхронной загрузки звука. Когда загрузка завершена, он выдает <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> событий.|  
|<xref:System.Media.SoundPlayer.Play%2A> метод|Воспроизведение звука, указанного в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойство в новом потоке.|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> метод|Воспроизведение звука, указанного в <xref:System.Media.SoundPlayer.SoundLocation%2A> или <xref:System.Media.SoundPlayer.Stream%2A> свойство в текущем потоке.|  
|<xref:System.Media.SoundPlayer.Stop%2A> метод|Останавливает воспроизведение звука.|  
|<xref:System.Media.SoundPlayer.LoadCompleted> событий|Возникает после попытки загрузки звука.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>