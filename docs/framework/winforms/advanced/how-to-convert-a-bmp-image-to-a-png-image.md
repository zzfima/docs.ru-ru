---
title: "Практическое руководство. Преобразование изображение из формата BMP в формат PNG"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 542dd132ece543b6a53a9e6d867b49fce4d15a58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>Практическое руководство. Преобразование изображение из формата BMP в формат PNG
Очень часто необходимо преобразовать изображение из одного формата в другой. Это легко сделать, вызвав метод <xref:System.Drawing.Image.Save%2A> класса <xref:System.Drawing.Image> и указав в качестве параметра <xref:System.Drawing.Imaging.ImageFormat> нужный формат файла.  
  
## <a name="example"></a>Пример  
 В примере ниже изображение в формате BMP загружается из типа и сохраняется в формате PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   приложение Windows Forms;  
  
-   ссылка на пространство имен `System.Drawing.Imaging`.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Применение кодировщиков и декодеров изображений в управляемом GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 [Типы растровых изображений](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
