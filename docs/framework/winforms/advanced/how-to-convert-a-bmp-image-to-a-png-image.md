---
title: "Практическое руководство. Преобразование изображение из формата BMP в формат PNG | Microsoft Docs"
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
  - "BMP - изображения, преобразование в PNG"
  - "форматы изображений, преобразование между"
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Преобразование изображение из формата BMP в формат PNG
Очень часто необходимо преобразовать изображение из одного формата в другой.  Это легко сделать, вызвав метод <xref:System.Drawing.Image.Save%2A> класса <xref:System.Drawing.Image> и указав в качестве параметра <xref:System.Drawing.Imaging.ImageFormat> нужный формат файла.  
  
## Пример  
 В примере ниже изображение в формате BMP загружается из типа и сохраняется в формате PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   приложение Windows Forms;  
  
-   ссылка на пространство имен `System.Drawing.Imaging`.  
  
## См. также  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Применение кодировщиков и декодеров изображений в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)   
 [Типы точечных рисунков](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)