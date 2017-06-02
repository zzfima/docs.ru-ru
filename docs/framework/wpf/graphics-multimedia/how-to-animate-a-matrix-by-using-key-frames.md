---
title: "Практическое руководство. Анимация матрицы с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, свойств Matrix с помощью ключевых кадров"
  - "ключевые кадры, анимация свойств Matrix"
  - "Matrix - свойства, анимация по ключевым кадрам"
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Анимация матрицы с помощью ключевых кадров
В этом примере демонстрируется анимация свойства <xref:System.Windows.Media.MatrixTransform.Matrix%2A> элемента управления <xref:System.Windows.Media.MatrixTransform> с помощью полных кадров.  
  
## Пример  
 В следующем примере класс <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> используется для анимации свойства <xref:System.Windows.Media.MatrixTransform.Matrix%2A> объекта <xref:System.Windows.Media.MatrixTransform>.  В примере используется объект <xref:System.Windows.Media.MatrixTransform> для преобразования внешнего вида и положения объекта <xref:System.Windows.Controls.Button>.  
  
 При анимации с использованием класса <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> создаются два полных кадра, с которыми выполняются следующие действия:  
  
1.  Анимация первого объекта <xref:System.Windows.Media.Matrix> в течение первых 0,2 секунды.  В этом примере изменяются свойства <xref:System.Windows.Media.Matrix.M11%2A> и <xref:System.Windows.Media.Matrix.M12%2A> объекта <xref:System.Windows.Media.Matrix>.  В результате изменения кнопка растягивается и наклоняется.  Также в примере изменяются свойства <xref:System.Windows.Media.Matrix.OffsetX%2A> и <xref:System.Windows.Media.Matrix.OffsetY%2A>, в результате чего изменяется положение кнопки.  
  
2.  Анимация второго объекта <xref:System.Windows.Media.Matrix>, начиная с 1,0 секунды.  Кнопка перемещается в другое положение. Растяжение и наклон кнопки отменяются.  
  
3.  Циклическое повторение анимации.  
  
> [!NOTE]
>  Полные кадры, производные от объекта <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>, создают резкие переходы между значениями, т.е. анимация выполняется рывками.  
  
 [!code-xml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>   
 <xref:System.Windows.Media.MatrixTransform>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)