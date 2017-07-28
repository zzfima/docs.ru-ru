---
title: "Практическое руководство. Получение списка установленных декодеров | Microsoft Docs"
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
  - "кодеки изображений, список"
  - "декодеры изображений, список"
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Получение списка установленных декодеров
Иногда требуется получить список установленных на компьютере декодеров, чтобы понять, может ли приложение читать изображение в виде файла того или иного формата.  У класса <xref:System.Drawing.Imaging.ImageCodecInfo> имеются статические методы <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>, позволяющие получить список доступных декодеров изображений.  Метод <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> возвращает массив объектов <xref:System.Drawing.Imaging.ImageCodecInfo>.  
  
## Пример  
 Следующий пример кода возвращает список установленных декодеров и значения их свойств.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Приложение Windows Forms.  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs>, являющийся параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Применение кодировщиков и декодеров изображений в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)