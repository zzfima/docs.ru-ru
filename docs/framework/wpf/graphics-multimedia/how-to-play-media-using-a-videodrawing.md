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
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="eb4f7-102">Практическое руководство. Воспроизведение мультимедиа с помощью объекта VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="eb4f7-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="eb4f7-103">Чтобы воспроизвести аудио- <xref:System.Windows.Media.VideoDrawing> или видеофайл, используйте <xref:System.Windows.Media.MediaPlayer>и.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="eb4f7-104">Есть два способа загрузки и воспроизведения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-104">There are two ways to load and play media.</span></span> <span data-ttu-id="eb4f7-105">Первый <xref:System.Windows.Media.MediaPlayer> — использовать <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.VideoDrawing> и сам по себе, а второй способ — создать <xref:System.Windows.Media.MediaPlayer> собственный для использования с и <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb4f7-106">При распространении мультимедиа с приложением, в отличие от изображений, файл мультимедиа нельзя использовать как ресурс проекта.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="eb4f7-107">Вместо этого в файле проекта необходимо выбрать тип мультимедиа `Content` и задать для `CopyToOutputDirectory` значение `PreserveNewest` или `Always`.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb4f7-108">Пример</span><span class="sxs-lookup"><span data-stu-id="eb4f7-108">Example</span></span>  
 <span data-ttu-id="eb4f7-109">В следующем примере используется <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> и для воспроизведения видеофайла один раз.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="eb4f7-110">Чтобы получить дополнительный контроль времени для носителя, используйте объект <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> с объектами и <xref:System.Windows.Media.VideoDrawing> .</span><span class="sxs-lookup"><span data-stu-id="eb4f7-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="eb4f7-111"><xref:System.Windows.Media.MediaTimeline> Позволяет указать, следует ли повторять воспроизведение видео.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb4f7-112">Пример</span><span class="sxs-lookup"><span data-stu-id="eb4f7-112">Example</span></span>  
 <span data-ttu-id="eb4f7-113">В следующем примере используется объект <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> с объектами и <xref:System.Windows.Media.VideoDrawing> для многократного воспроизведения видео.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="eb4f7-114">Обратите внимание, что при использовании <xref:System.Windows.Media.MediaTimeline>среды используется интерактивный <xref:System.Windows.Media.Animation.ClockController> метод, возвращенный <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> из свойства объекта для управления воспроизведением мультимедиа вместо интерактивных методов <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="eb4f7-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4f7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="eb4f7-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="eb4f7-116">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="eb4f7-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
