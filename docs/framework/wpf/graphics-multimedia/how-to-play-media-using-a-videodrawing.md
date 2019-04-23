---
title: Практическое руководство. Воспроизведение мультимедиа с помощью объекта VideoDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 186c9ae8167dafd09f029418c1d23f81f7a9e906
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203617"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="f7101-102">Практическое руководство. Воспроизведение мультимедиа с помощью объекта VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="f7101-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="f7101-103">Для воспроизведения аудио-или видео, используйте <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="f7101-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="f7101-104">Есть два способа загрузки и воспроизведения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="f7101-104">There are two ways to load and play media.</span></span> <span data-ttu-id="f7101-105">Первый заключается в использовании <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> , а второй способ состоит в создании собственных <xref:System.Windows.Media.MediaTimeline> для использования с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="f7101-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7101-106">При распространении мультимедиа с приложением, в отличие от изображений, файл мультимедиа нельзя использовать как ресурс проекта.</span><span class="sxs-lookup"><span data-stu-id="f7101-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="f7101-107">Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.</span><span class="sxs-lookup"><span data-stu-id="f7101-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7101-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f7101-108">Example</span></span>  
 <span data-ttu-id="f7101-109">В следующем примере используется <xref:System.Windows.Media.VideoDrawing> и <xref:System.Windows.Media.MediaPlayer> для однократного воспроизведения видеофайла.</span><span class="sxs-lookup"><span data-stu-id="f7101-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="f7101-110">Чтобы получить дополнительное управление временем для мультимедиа, используйте <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> объектов.</span><span class="sxs-lookup"><span data-stu-id="f7101-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="f7101-111"><xref:System.Windows.Media.MediaTimeline> Позволяет указать, следует ли повторять видео.</span><span class="sxs-lookup"><span data-stu-id="f7101-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7101-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f7101-112">Example</span></span>  
 <span data-ttu-id="f7101-113">В следующем примере используется <xref:System.Windows.Media.MediaTimeline> с <xref:System.Windows.Media.MediaPlayer> и <xref:System.Windows.Media.VideoDrawing> объекты для воспроизведения видео.</span><span class="sxs-lookup"><span data-stu-id="f7101-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="f7101-114">Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>, интерактивный <xref:System.Windows.Media.Animation.ClockController> возвращаемые <xref:System.Windows.Media.Animation.Clock.Controller%2A> свойство <xref:System.Windows.Media.MediaClock> для управления воспроизведением мультимедиа, а не интерактивные методы <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="f7101-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7101-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f7101-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="f7101-116">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="f7101-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
