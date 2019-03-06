---
title: Практическое руководство. Управление элементом MediaElement (воспроизведение, пауза, остановка, громкость и скорость)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: 7fe8107f7b5b65f00f2c5ac029f806aeba758d20
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368510"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="188e1-102">Практическое руководство. Управление элементом MediaElement (воспроизведение, пауза, остановка, громкость и скорость)</span><span class="sxs-lookup"><span data-stu-id="188e1-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="188e1-103">В следующем примере показано, как управлять воспроизведением мультимедиа с помощью <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="188e1-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="188e1-104">В примере создается простой мультимедийный проигрыватель, который позволяет воспроизводить, приостановить, остановить и прокрутку вперед и назад на носителе, а также установить значение коэффициента громкость и скорость.</span><span class="sxs-lookup"><span data-stu-id="188e1-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="188e1-105">Пример</span><span class="sxs-lookup"><span data-stu-id="188e1-105">Example</span></span>  
 <span data-ttu-id="188e1-106">Приведенный ниже код создает пользовательский Интерфейс.</span><span class="sxs-lookup"><span data-stu-id="188e1-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="188e1-107"><xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Свойство <xref:System.Windows.Controls.MediaElement> должно быть присвоено `Manual` чтобы иметь возможность интерактивно остановки, приостановки и воспроизведения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="188e1-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="188e1-108">Пример</span><span class="sxs-lookup"><span data-stu-id="188e1-108">Example</span></span>  
 <span data-ttu-id="188e1-109">Приведенный ниже код реализует функциональные возможности элементов управления пользовательского интерфейса примера.</span><span class="sxs-lookup"><span data-stu-id="188e1-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="188e1-110"><xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, И <xref:System.Windows.Controls.MediaElement.Stop%2A> методы используются для соответственно воспроизведения, приостановки и остановки мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="188e1-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="188e1-111">Изменение <xref:System.Windows.Controls.MediaElement.Position%2A> свойство <xref:System.Windows.Controls.MediaElement> позволяет быстро перемещаться на носителе.</span><span class="sxs-lookup"><span data-stu-id="188e1-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="188e1-112">Наконец <xref:System.Windows.Controls.MediaElement.Volume%2A> и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> свойства используются для настройки громкости и скорости воспроизведения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="188e1-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="188e1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="188e1-113">See also</span></span>
- [<span data-ttu-id="188e1-114">Управление элементом MediaElement с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="188e1-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
