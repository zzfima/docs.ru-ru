---
title: "Практическое руководство. Задание источника преобразования с помощью относительных значений | Microsoft Docs"
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
  - "графика, начала Transform"
  - "начала Transform"
  - "Transform, начала"
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Задание источника преобразования с помощью относительных значений
В этом примере показано использование относительных значений для указания <xref:System.Windows.UIElement.RenderTransform%2A>, применяемого к <xref:System.Windows.FrameworkElement>.  
  
 При повороте, масштабировании или [наклоне](GTMT) <xref:System.Windows.FrameworkElement> с помощью свойства <xref:System.Windows.UIElement.RenderTransform%2A>, значение по умолчанию применяет преобразование к верхнему левому углу элемента.  Если вы хотите повернуть, отмасштабировать или наклонить объект относительно центра элемента, можно установить центр элемента центром преобразования.  Однако, это решение требует знания размера элемента.  Простым способом применения преобразования к центру элемента является установка его свойства <xref:System.Windows.UIElement.RenderTransformOrigin%2A> в значение \(0,5, 0,5\), вместо установки центрального значения преобразования.  
  
## Пример  
 В следующем примере используется <xref:System.Windows.Media.RotateTransform>для поворота <xref:System.Windows.Controls.Button> на 45 градусов по часовой стрелке.  Поскольку в примере не задан центр, кнопка поворачивается вокруг точки \(0, 0\), то есть верхнего левого угла.  <xref:System.Windows.Media.RotateTransform> применяется к свойству <xref:System.Windows.UIElement.RenderTransform%2A>.  
  
 На следующем рисунке показан результат преобразования для следующего примера.  
  
 ![Преобразованная кнопка с использованием RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
Поворот на 45 градусов по часовой стрелке с использованием свойства RenderTransform  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 В следующем примере также используется объект <xref:System.Windows.Media.RotateTransform> для поворота объекта <xref:System.Windows.Controls.Button> на 45 градусов по часовой стрелке, а также присваивается значение \(0,5,0,5\) свойству <xref:System.Windows.UIElement.RenderTransformOrigin%2A> кнопки.  В результате поворот выполняется относительно центра кнопки, а не ее верхнего левого угла.  
  
 На следующем рисунке показан результат преобразования для следующего примера.  
  
 ![Кнопка, преобразованная по центру](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
Поворот на 45 градусов с использованием свойство RenderTransform с RenderTransformOrigin, равным \(0,5, 0,5\)  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Дополнительные сведения об объектах <xref:System.Windows.FrameworkElement> см. в разделе [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.Transform>   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)