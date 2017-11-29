---
title: "Практическое руководство. Воспроизведение мультимедиа с помощью VideoDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2753db8e06c8c1b50c6e5cee17330d421e88511f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-media-using-a-videodrawing"></a>Практическое руководство. Воспроизведение мультимедиа с помощью VideoDrawing
Чтобы воспроизведение звука и видео, используйте <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer>. Есть два способа загрузки и воспроизведения мультимедиа. Первый заключается в использовании <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> , а второй способ состоит в создании собственных <xref:System.Windows.Media.MediaTimeline> для использования с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  При распространении мультимедиа с приложением, в отличие от изображений, файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer> для воспроизведения видео файл один раз.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Чтобы получить дополнительное управление временем для мультимедиа, используйте <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> объектов. <xref:System.Windows.Media.MediaTimeline> Позволяет указать, следует ли повторять видео.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> объекты для воспроизведения видео.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>, используется интерактивный <xref:System.Windows.Media.Animation.ClockController> , возвращенные <xref:System.Windows.Media.Animation.Clock.Controller%2A> свойство <xref:System.Windows.Media.MediaClock> управления воспроизведением мультимедиа, вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.VideoDrawing>  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
