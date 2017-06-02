---
title: "Применение кодировщиков и декодеров изображений в управляемом GDI+ | Microsoft Docs"
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
  - "декодеры изображений, использование"
  - "кодировщики изображений, использование"
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Применение кодировщиков и декодеров изображений в управляемом GDI+
В пространстве имен <xref:System.Drawing> имеются классы <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap>, которые служат для хранения изображений и управления ими.  С помощью кодировщиков изображений [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно сохранять изображения из памяти на диск. С помощью декодеров изображений [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно загружать изображения с диска в память.  Кодировщик выполняет трансляцию данных в объекте <xref:System.Drawing.Image> или <xref:System.Drawing.Bitmap> в формат файла для сохранения на диске.  Декодер выполняет трасляцию данных в файле на диске в формат, который требуется для работы объектов <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap>.  
  
 В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] имеются встроенные кодировщики и декодеры, поддерживающие следующие типы файлов:  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] также имеются встроенные декодеры, поддерживающие следующие типы файлов:  
  
-   WMF  
  
-   EMF  
  
-   ICON  
  
 Более подробно кодировщики и декодеры описаны в следующих разделах:  
  
## В этом подразделе  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 Получение списка доступных на компьютере кодировщиков.  
  
 [Практическое руководство. Получение списка установленных декодеров](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 Получение списка доступных на компьютере декодеров.  
  
 [Практическое руководство. Определение параметров, поддерживаемых кодировщиком](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Получение списка параметров <xref:System.Drawing.Imaging.EncoderParameters>, поддерживаемых кодировщиком.  
  
 [Практическое руководство. Преобразование изображение из формата BMP в формат PNG](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 Сохранение изображения в другом формате хранения изображений.  
  
 [Практическое руководство. Установка уровня сжатия JPEG](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 Изменение уровня качества изображения.  
  
## Ссылка  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## Связанные подразделы  
 [Управляемый код GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)