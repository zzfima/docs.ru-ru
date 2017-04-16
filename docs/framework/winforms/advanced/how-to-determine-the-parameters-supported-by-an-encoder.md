---
title: "Практическое руководство. Определение параметров, поддерживаемых кодировщиком | Microsoft Docs"
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
  - "параметры кодировщика, определение поддерживаемых"
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Определение параметров, поддерживаемых кодировщиком
Параметры изображения, например его качество или уровень сжатия, можно менять, но для этого необходимо знать, какие параметры поддерживает выбранный кодировщик.  У класса <xref:System.Drawing.Image> имеется метод <xref:System.Drawing.Image.GetEncoderParameterList%2A>, позволяющие определять список параметров, поддерживаемых тем или иным кодировщиком.  Кодировщик определяется идентификатором GUID.  Метод <xref:System.Drawing.Image.GetEncoderParameterList%2A> возвращает массив объектов <xref:System.Drawing.Imaging.EncoderParameter>.  
  
## Пример  
 Результатом выполнения следующего примера кода будет список параметров, поддерживаемых кодировщиком JPEG.  Чтобы определить категорию каждого параметра, используйте список категорий параметров и связанные с ними идентификаторы GUID в классе <xref:System.Drawing.Imaging.Encoder>.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Приложение Windows Forms.  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs>, являющийся параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Типы точечных рисунков](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [Применение кодировщиков и декодеров изображений в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)