---
title: Практическое руководство. Управление элементом "MediaElement" (воспроизведение, пауза, остановка, громкость и скорость)
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
ms.openlocfilehash: beeddc658f16d8b52142a8a79f9c61e4f7070b01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Практическое руководство. Управление элементом "MediaElement" (воспроизведение, пауза, остановка, громкость и скорость)
Следующий пример показывает способ управления воспроизведением мультимедиа с помощью <xref:System.Windows.Controls.MediaElement>. В примере создается простой проигрыватель для воспроизведения, приостановить, остановить и прокрутку вперед и назад на носителе, а также настроить громкость и скорость воспроизведения.  
  
## <a name="example"></a>Пример  
 В следующем примере кода создается пользовательский Интерфейс.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Свойство <xref:System.Windows.Controls.MediaElement> должно быть присвоено `Manual` чтобы иметь возможность интерактивно остановки, приостановки и воспроизведения мультимедиа.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода реализует функциональные возможности элементов управления пользовательского интерфейса образца. <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, И <xref:System.Windows.Controls.MediaElement.Stop%2A> методы используются для соответственно воспроизведения, приостановки и остановки мультимедиа. Изменение <xref:System.Windows.Controls.MediaElement.Position%2A> свойство <xref:System.Windows.Controls.MediaElement> позволяет быстро перемещаться на носителе. Наконец <xref:System.Windows.Controls.MediaElement.Volume%2A> и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> свойства используются для корректировки скорости тома и воспроизведения мультимедиа.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Управление элементом MediaElement с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
