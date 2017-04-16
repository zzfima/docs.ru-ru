---
title: "Как применить преобразования к тексту | Microsoft Docs"
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
  - "повернутый текст"
  - "масштабированный текст"
  - "затененный текст"
  - "наклоненный текст"
  - "преобразования в тексте"
  - "переведенный текст"
  - "оформление, повернутый текст"
  - "оформление, масштабированный текст"
  - "оформление, затененный текст"
  - "оформление, наклоненный текст"
  - "оформление, преобразования"
  - "оформление, переведенный текст"
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Как применить преобразования к тексту
Преобразования могут изменить отображение текста в приложении.  В следующем примере используются различные типы преобразований при отрисовке, которые влияют на отображение текста в элементе управления <xref:System.Windows.Controls.TextBlock>.  
  
## Пример  
 В следующем примере показан текст, повернутый относительно заданной точки в двумерной плоскости x\-y.  
  
 ![Текст, повернутый с использованием RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.png "TransformedText01")  
Пример текста, повернутого на 90 градусов  
  
 В следующем примере кода для поворота текста используется <xref:System.Windows.Media.RotateTransform>.  Значение 90 свойства <xref:System.Windows.Media.RotateTransform.Angle%2A> поворачивает элемента на 90 градусов по часовой стрелке.  
  
 [!code-xml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 Следующий пример показывает вторую строку текста, масштабированную на 150% вдоль оси x, и третью строку текста, масштабированную на 150% вдоль оси y.  
  
 ![Текст, масштабируемый с использованием ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.png "TransformedText02")  
Пример масштабированного текста  
  
 В следующем примере кода используется объект <xref:System.Windows.Media.ScaleTransform> для масштабирования текста из исходного размера.  
  
 [!code-xml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Масштабирование текста отличается от увеличения размера шрифта текста.  Размеры шрифтов вычисляются независимо друг от друга, чтобы обеспечить лучшее разрешение в разных размерах.  Масштабируемой текст, в свою очередь, сохраняет пропорции исходного размера текста.  
  
 В следующем примере показан текст, наклоненный вдоль оси x.  
  
 ![Текст, искаженный с использованием SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.png "TransformedText03")  
Пример наклоненного текста  
  
 В следующем примере кода используется объект <xref:System.Windows.Media.SkewTransform> для наклона текста.  Наклон, также известный как сдвиг, является преобразованием, при котором пространство координат увеличивается неравномерно.  В этом примере две текстовые строки поворачиваются на \-30 ° и 30° вдоль оси координат x.  
  
 [!code-xml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 В следующем примере показан переведенный текст \(или перемещенный\) вдоль оси x и y.  
  
 ![Смещение текста с использованием TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.png "TransformedText04")  
Пример переведенного текста  
  
 В следующем примере кода используется объект <xref:System.Windows.Media.TranslateTransform> для смещения текста.  В этом примере немного смещенная копия текста под основным текстом создает эффект тени.  
  
 [!code-xml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  Объект <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> предоставляет широкий набор возможностей с использованием эффекта тени.  Дополнительные сведения см. в разделе [Создание текста с тенью](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).  
  
## См. также  
 [Применение анимаций к тексту](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)