---
title: "Практическое руководство. Применение анимаций к тексту | Microsoft Docs"
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
  - "анимация, текст"
  - "оформление, анимации"
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Применение анимаций к тексту
Анимация может изменять отображение и вид текста в приложении.  В следующих примерах используются различные виды анимации, влияющие на отображение текста в элементе управления <xref:System.Windows.Controls.TextBlock>.  
  
## Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации ширины блока текста.  Значение ширины изменяет ширину блока текста на 0 на протяжении 10 секунд, а затем значение ширины возвращается.  Анимация этого типа создает эффект постепенной смены изображения.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimation> используется для анимации непрозрачности блока текста.  Значение непрозрачности изменяется с 1.0 до 0 на протяжении 5 секунд, а затем значение непрозрачности возвращается.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Следующая диаграмма показывает влияние <xref:System.Windows.Controls.TextBlock> на изменение непрозрачности элемента управления с `1.00` на `0.00` в течение 5\-секундного интервала, заданного свойством <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Изменение непрозрачности текста с 1,00 до 0,00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
Изменение непрозрачности текста с 1,00 до 0,00  
  
 В следующем примере для анимации основного цвета блока текста используется <xref:System.Windows.Media.Animation.ColorAnimation>.  Значение основного цвета изменяется с одного цвета на другой цвет в течение 5 секунд, а затем значение цвета возвращается.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 В следующем примере для поворота текстового блока используется <xref:System.Windows.Media.Animation.DoubleAnimation>.  Текстовый блок выполняет полный поворот в течение 20 секунд, а затем поворот повторяется.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)