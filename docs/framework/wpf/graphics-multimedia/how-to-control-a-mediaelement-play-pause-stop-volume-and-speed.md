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
ms.openlocfilehash: cde7c32b48dff3d6d054e700b2f95771ba3b3773
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930160"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Практическое руководство. Управление элементом MediaElement (воспроизведение, пауза, остановка, громкость и скорость)
В следующем примере показано, как управлять воспроизведением мультимедиа с помощью <xref:System.Windows.Controls.MediaElement>. В этом примере создается простой проигрыватель мультимедиа, позволяющий играть, приостанавливать, останавливать и пропускать назад и вперед, а также изменять соотношение громкости и скорости.  
  
## <a name="example"></a>Пример  
 Приведенный ниже код создает пользовательский интерфейс.  
  
> [!NOTE]
> Свойство объекта <xref:System.Windows.Controls.MediaElement> должно быть установлено в значение `Manual` , чтобы иметь возможность интерактивно останавливать, приостанавливать и воспроизводить мультимедиа. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Пример  
 Приведенный ниже код реализует функциональные возможности примеров элементов управления пользовательского интерфейса. Методы <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> и<xref:System.Windows.Controls.MediaElement.Stop%2A> используются соответственно для воспроизведения, приостановки и остановки мультимедиа. <xref:System.Windows.Controls.MediaElement.Position%2A> Изменение свойства<xref:System.Windows.Controls.MediaElement> объекта позволяет пропускать его на носителе. Наконец, <xref:System.Windows.Controls.MediaElement.Volume%2A> свойства и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> используются для настройки громкости и скорости воспроизведения носителя.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>См. также

- [Управление элементом MediaElement с помощью раскадровки](how-to-control-a-mediaelement-by-using-a-storyboard.md)
