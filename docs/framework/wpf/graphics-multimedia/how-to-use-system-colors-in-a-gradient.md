---
title: "Практическое руководство. Использование системных цветов в градиенте | Microsoft Docs"
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
  - "градиенты, системные цвета"
  - "системные цвета в градиентах"
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Использование системных цветов в градиенте
Чтобы использовать системный цвет в градиенте, используются статические свойства класса <xref:System.Windows.SystemColors> *\<SystemColor\>*Color и *\<SystemColor\>*ColorKey для получения ссылки на цвет, где *\<SystemColor\>* является именем необходимого системного цвета.  Используйте свойства *\<SystemColor\>*ColorKey, если необходимо создать динамическую ссылку, которая обновляется автоматически по мере изменения темы системы.  В противном случае, используйте свойства *\<SystemColor\>*Color.  
  
## Пример  
 В следующем примере используются динамические ресурсы цвета системы для создания градиента.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 В следующем примере используются статические ресурсы цвета системы для создания градиента.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## См. также  
 <xref:System.Windows.SystemColors>   
 [Закраска области с помощью системной кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)