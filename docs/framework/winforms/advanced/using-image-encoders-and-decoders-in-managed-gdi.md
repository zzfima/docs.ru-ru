---
title: "Применение кодировщиков и декодеров изображений в управляемом GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64384e3c283b6596e36d5b2bd583a304faf080b4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>Применение кодировщиков и декодеров изображений в управляемом GDI+
<xref:System.Drawing> Пространство имен предоставляет <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap> классов для хранения изображений и управления ими. С помощью кодировщиков изображений в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно сохранять изображения из памяти на диск. С помощью декодеров изображений в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно загружать изображения с диска в память. Кодировщик преобразует данные в <xref:System.Drawing.Image> или <xref:System.Drawing.Bitmap> объект в формат файла выделенного диска. Декодер преобразует данные в файл на диске в формат, требуемый <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap> объектов.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]имеет встроенные кодировщиков и декодеров, которые поддерживают следующие типы файлов:  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   Формат PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]также имеются встроенные декодеры, которые поддерживают следующие типы файлов:  
  
-   WMF  
  
-   EMF  
  
-   ЗНАЧОК  
  
 Кодировщиков и декодеров более подробно рассматривается в следующих разделах:  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 Описывает способы просмотра кодировщиков, доступными на компьютере.  
  
 [Практическое руководство. Получение списка установленных декодеров](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 Описывает способы просмотра декодеров на компьютере.  
  
 [Практическое руководство. Определение параметров, поддерживаемых кодировщиком](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Описывает способы просмотра <xref:System.Drawing.Imaging.EncoderParameters> поддерживается кодировщиком.  
  
 [Практическое руководство. Преобразование изображение из формата BMP в формат PNG](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 Описывает, как сохранить образ в формате другое изображение.  
  
 [Практическое руководство. Установка уровня сжатия JPEG](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 Описывает, как изменить уровень качества изображения.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Управляемый код GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
