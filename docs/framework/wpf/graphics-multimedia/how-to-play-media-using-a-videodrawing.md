---
title: "Практическое руководство. Воспроизведение мультимедиа с помощью VideoDrawing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "классы, MediaPlayer"
  - "классы, VideoDrawing"
  - "MediaPlayer - класс"
  - "воспроизведение мультимедиа"
  - "VideoDrawing - класс"
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Воспроизведение мультимедиа с помощью VideoDrawing
Для воспроизведения аудио\- и видеофайлов следует использовать <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer>.  Существуют два способа загрузки и воспроизведения файлов мультимедиа.  Первый способ заключается в использовании <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>, а второй — в создании собственных <xref:System.Windows.Media.MediaTimeline> для использования с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  При передаче файлов мультимедиа приложениям файл мультимедиа, в отличие от изображений, нельзя использовать в качестве ресурса проекта.  Вместо этого в файле проекта необходимо задать для типа мультимедиа значение `Content` и для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.  
  
## Пример  
 В следующем примере <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer> используются для однократного воспроизведения видеофайла.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Чтобы получить дополнительное управление временем для мультимедиа, используйте <xref:System.Windows.Media.MediaTimeline> с объектами <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>.  <xref:System.Windows.Media.MediaTimeline> позволяет задать повтор воспроизведения видеофайла.  
  
## Пример  
 В следующем примере <xref:System.Windows.Media.MediaTimeline> используется с объектами <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> для циклического воспроизведения видео.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>, используется интерактивный <xref:System.Windows.Media.Animation.ClockController>, который возвращается свойством <xref:System.Windows.Media.Animation.Clock.Controller%2A> для <xref:System.Windows.Media.MediaClock> и позволяет управлять воспроизведением мультимедиа, вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.  
  
## См. также  
 <xref:System.Windows.Media.VideoDrawing>   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)