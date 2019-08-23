---
title: Практическое руководство. Воспроизведение мультимедиа с помощью объекта VideoDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956953"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>Практическое руководство. Воспроизведение мультимедиа с помощью объекта VideoDrawing
Чтобы воспроизвести аудио- <xref:System.Windows.Media.VideoDrawing> или видеофайл, используйте <xref:System.Windows.Media.MediaPlayer>и. Есть два способа загрузки и воспроизведения мультимедиа. Первый <xref:System.Windows.Media.MediaPlayer> — использовать <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.VideoDrawing> и сам по себе, а второй способ — создать <xref:System.Windows.Media.MediaPlayer> собственный для использования с и <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> При распространении мультимедиа с приложением, в отличие от изображений, файл мультимедиа нельзя использовать как ресурс проекта. Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> и для воспроизведения видеофайла один раз.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Чтобы получить дополнительный контроль времени для носителя, используйте объект <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> с объектами и <xref:System.Windows.Media.VideoDrawing> . <xref:System.Windows.Media.MediaTimeline> Позволяет указать, следует ли повторять воспроизведение видео.  
  
## <a name="example"></a>Пример  
 В следующем примере используется объект <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> с объектами и <xref:System.Windows.Media.VideoDrawing> для многократного воспроизведения видео.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>среды используется интерактивный <xref:System.Windows.Media.Animation.ClockController> метод, возвращенный <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> из свойства объекта для управления воспроизведением мультимедиа вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.VideoDrawing>
- [Обзор объектов Drawing](drawing-objects-overview.md)
