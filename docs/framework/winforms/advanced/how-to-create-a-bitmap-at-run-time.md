---
title: "Практическое руководство. Создание растрового изображения во время выполнения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "растровые изображения, создание"
  - "растровые изображения, примеры [Visual Basic]"
ms.assetid: 737bae30-e599-4e1d-bf30-bab8280b32be
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Создание растрового изображения во время выполнения
В этом примере демонстрируется создание объекта <xref:System.Drawing.Bitmap> и рисование в нем, после чего объект отображается на существующей форме Windows Forms в элементе управления <xref:System.Windows.Forms.PictureBox>.  
  
## Пример  
 [!code-csharp[System.Drawing.CreateBitmapAtRuntime#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CreateBitmapAtRuntime/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.CreateBitmapAtRuntime#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CreateBitmapAtRuntime/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Форма Windows Form, импортирующая сборки System, System.Drawing и System.Windows.Forms.  
  
## См. также  
 <xref:System.Drawing.Bitmap>   
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)