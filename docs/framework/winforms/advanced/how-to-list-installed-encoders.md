---
title: "Практическое руководство. Получение списка установленных кодировщиков | Microsoft Docs"
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
  - "кодировщики изображений, список"
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Получение списка установленных кодировщиков
Иногда требуется получить список установленных на компьютере кодировщиков, чтобы понять, может ли приложение сохранять изображение в виде файла того или иного формата.  У класса <xref:System.Drawing.Imaging.ImageCodecInfo> имеются статические методы <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>, позволяющие получить список доступных кодировщиков изображений.  Метод <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> возвращает массив объектов <xref:System.Drawing.Imaging.ImageCodecInfo>.  
  
## Пример  
 Следующий пример кода возвращает список установленных кодировщиков и значения их свойств.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Приложение Windows Forms.  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs>, являющийся параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Практическое руководство. Получение списка установленных декодеров](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)   
 [Применение кодировщиков и декодеров изображений в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)