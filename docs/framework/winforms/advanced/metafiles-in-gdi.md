---
title: "Метафайлы в GDI+ | Microsoft Docs"
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
  - "GDI+, метафайлы"
  - "изображения [Windows Forms], метафайлы"
  - "метафайлы"
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Метафайлы в GDI+
В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] имеется класс <xref:System.Drawing.Imaging.Metafile>, позволяющий записывать и отображать метафайлы.  Метафайл, также называемый векторным рисунком, — это изображение, сохраненное в виде последовательности команд и параметров рисования.  Команды и параметры, сохраненные в объекте <xref:System.Drawing.Imaging.Metafile>, могут быть сохранены в памяти или записаны в файл или в поток.  
  
## Форматы метафайлов  
 Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] позволяет отображать метафайлы, сохраненные в одном из перечисленных ниже форматов.  
  
-   WMF \(Windows Metafile — метафайл Windows\)  
  
-   EMF \(Enhanced Metafile —расширенный метафайл\)  
  
-   EMF\+  
  
 Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] позволяет сохранять метафайлы в форматах EMF и EMF\+, но не в формате WMF.  
  
 Формат EMF\+ является расширением формата EMF, позволяющим сохранять записи [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Существует два варианта формата EMF\+: EMF\+ Only и EMF\+ Dual.  Метафайлы EMF\+ Only содержат только записи [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Такие метафайлы могут отображаться интерфейсом [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], но не интерфейсом [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  Метафайлы EMF\+ Dual содержат записи [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и записи [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  Каждая запись [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] хранится в метафайле EMF\+ Dual вместе с альтернативной записью [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  Такие метафайлы могут отображаться как интерфейсом [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], так и интерфейсом [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 Приведенный ниже пример демонстрирует отображение метафайла, ранее сохраненного в файле.  Метафайл отображается с привязкой его левого верхнего края к точке с координатами \(100, 100\).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)