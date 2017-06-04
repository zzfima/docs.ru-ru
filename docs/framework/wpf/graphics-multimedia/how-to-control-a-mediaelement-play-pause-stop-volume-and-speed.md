---
title: "Практическое руководство. Управление элементом &quot;MediaElement&quot; (воспроизведение, пауза, остановка, громкость и скорость) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "управление воспроизведением мультимедиа"
  - "носители, управление воспроизведением"
  - "мультимедиа, управление воспроизведением мультимедиа"
  - "воспроизведение мультимедиа, управление"
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Управление элементом &quot;MediaElement&quot; (воспроизведение, пауза, остановка, громкость и скорость)
В следующем примере показано управление воспроизведением мультимедиа с помощью <xref:System.Windows.Controls.MediaElement>.  В примере создается простой проигрыватель, позволяющий воспроизводить мультимедиа, включать паузу, остановку, прокрутку вперед и назад, а также настраивать громкость и скорость воспроизведения.  
  
## Пример  
 Следующий код создает пользовательский интерфейс.  
  
> [!NOTE]
>  Для свойства <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> объекта <xref:System.Windows.Controls.MediaElement> должно быть установлено значение `Manual`, чтобы иметь возможность интерактивно останавливать, включать паузу и воспроизводить мультимедиа.  
  
 [!code-xml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## Пример  
 Приведенный ниже код реализует функциональные возможности элементов управления пользовательского интерфейса примера.  Методы <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> и <xref:System.Windows.Controls.MediaElement.Stop%2A> используются соответственно для осуществления воспроизведения, паузы и остановки мультимедиа.  Изменение свойства <xref:System.Windows.Controls.MediaElement.Position%2A> объекта <xref:System.Windows.Controls.MediaElement> позволяет включить прокрутку мультимедиа.  Наконец, свойства <xref:System.Windows.Controls.MediaElement.Volume%2A> и <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> используются для настройки громкости и скорости воспроизведения.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## См. также  
 [Управление элементом MediaElement с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)