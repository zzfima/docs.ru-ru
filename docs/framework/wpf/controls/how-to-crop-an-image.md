---
title: "Практическое руководство. Обрезка изображения | Microsoft Docs"
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
  - "классы, CroppedBitmap"
  - "CroppedBitmap - класс"
  - "обрезка изображений"
  - "изображения, обрезка"
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Обрезка изображения
В этом примере показано, как обрезать изображение с помощью элемента <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 В основном, элемент <xref:System.Windows.Media.Imaging.CroppedBitmap> используется при кодировании обрезанной версии изображения для сохранения в файле.  В разделе [Create a Clip Region](http://msdn.microsoft.com/ru-ru/56e4bed6-78d7-4292-b917-d72d0b3e4376) описано, как обрезать изображение для вывода на экран.  
  
## Пример  
 Следующий [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] определяет ресурсы, используемые в примере, показанном ниже.  
  
 [!code-xml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 В следующем примере создается изображение, в качестве источника использующее <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 [!code-xml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 Элемент <xref:System.Windows.Media.Imaging.CroppedBitmap> может также служить источником для другого элемента <xref:System.Windows.Media.Imaging.CroppedBitmap>, образуя цепочку обрезания.  Обратите внимание,что <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> использует значения, которые относятся к обрезанному точечному рисунку, а не к первоначальному изображению.  
  
 [!code-xml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## См. также  
 [Create a Clip Region](http://msdn.microsoft.com/ru-ru/56e4bed6-78d7-4292-b917-d72d0b3e4376)