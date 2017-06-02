---
title: "Практическое руководство. Установка длительности анимации | Microsoft Docs"
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
  - "анимация, duration"
  - "анимации - длительность"
  - "Временные шкалы, описание"
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Установка длительности анимации
<xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени, продолжительность которого определяется <xref:System.Windows.Duration> шкалы времени.  Когда <xref:System.Windows.Media.Animation.Timeline> достигает конца, воспроизведение прекращается.  Если <xref:System.Windows.Media.Animation.Timeline> имеет дочерние шкалы времени, то они также останавливают воспроизведение.  В случае анимации <xref:System.Windows.Duration> определяет, как долго анимация выполняет переход от ее начального значения до конечного.  
  
 Можно задать <xref:System.Windows.Duration> с определенным, ограниченным временем или специальными значениями <xref:System.Windows.Duration.Automatic%2A> или <xref:System.Windows.Duration.Forever%2A>.  Длительность анимации всегда должна быть значением времени, поскольку анимация всегда должна иметь определенную, ограниченную длину — в противном случае анимация не будет знать, каким образом осуществляется переход между ее значениями.  Шкалы времени контейнера \(объекты <xref:System.Windows.Media.Animation.TimelineGroup>\), такие как <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.ParallelTimeline>, имеют продолжительность по умолчанию <xref:System.Windows.Duration.Automatic%2A>, то есть они автоматически завершаются после того, как их последний дочерний элемент останавливает воспроизведение.  
  
 В следующем примере анимируется ширина, высота и заполнение цветом <xref:System.Windows.Shapes.Rectangle>.  Длительность, установленная для временной шкалы анимации или контейнера, оказывает влияние на эффекты анимации, включая управление скоростью анимации, замену значения продолжительности для дочерних шкал времени на значение продолжительности для шкалы времени контейнера.  
  
## Пример  
 [!code-xml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## См. также  
 <xref:System.Windows.Duration>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)