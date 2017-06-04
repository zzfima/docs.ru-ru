---
title: "Практическое руководство. Закраска области с помощью системной кисти | Microsoft Docs"
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
  - "кисти, рисование с помощью системных кистей"
  - "рисование, с помощью системных кистей"
  - "системные кисти, рисование с помощью"
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Закраска области с помощью системной кисти
Класс <xref:System.Windows.SystemColors> предоставляет доступ к системной кисти и системным цветам, таким как <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A> и <xref:System.Windows.SystemColors.DesktopBrush%2A>.  Системная кисть является объектом <xref:System.Windows.Media.SolidColorBrush>, закрашивающим область указанным системным цветом.  Системная кисть всегда дает сплошную заливку; она не может использоваться для создания градиентной заливки.  
  
 Можно использовать системные кисти либо как статические, либо как динамические ресурсы.  Динамические ресурсы используются при необходимости автоматического обновления кисти, если пользователь изменяет системную кисть во время выполнения приложения; в противном случае используются статические ресурсы.  Класс SystemColors содержит разнообразные статические свойства, которые следуют строгому правилу именования:  
  
-   *\<SystemColor\>*Brush  
  
     Получает статическую ссылку на <xref:System.Windows.Media.SolidColorBrush> указанного системного цвета.  
  
-   *\<SystemColor\>*BrushKey  
  
     Получает динамическую ссылку на <xref:System.Windows.Media.SolidColorBrush> указанного системного цвета.  
  
-   *\<SystemColor\>*Color  
  
     Получает статическую ссылку на структуру <xref:System.Windows.Media.Color> указанного системного цвета.  
  
-   *\<SystemColor\>*ColorKey  
  
     Получает динамическую ссылку на структуру <xref:System.Windows.Media.Color> указанного системного цвета.  
  
 Системный цвет представляет собой структуру <xref:System.Windows.Media.Color>, которая может быть использована для настройки кисти.  Например, можно создать градиент с помощью системных цветов, задав свойства <xref:System.Windows.Media.GradientStop.Color%2A> градиента объекта <xref:System.Windows.Media.LinearGradientBrush> с системными цветами.  Пример см. в разделе [Использование системных цветов в градиенте](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## Пример  
 В следующем примере используется динамическая ссылка системной кисти для установки фона кнопки.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 В следующем примере с помощью статической ссылки системной кисти устанавливается фон кнопки.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Пример, показывающий, как использовать системный цвет в градиенте, см. в разделе [Использование системных цветов в градиенте](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## См. также  
 [Использование системных цветов в градиенте](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)