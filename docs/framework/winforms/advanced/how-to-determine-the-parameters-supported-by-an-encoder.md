---
title: "Практическое руководство. Определение параметров, поддерживаемых кодировщиком"
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
helpviewer_keywords: encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3304adc9ab22d12905bd2a6c3739d909387d82cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Практическое руководство. Определение параметров, поддерживаемых кодировщиком
Можно настроить параметры изображения, такие как качество и уровня сжатия, но необходимо знать, какие параметры поддерживаются кодировщиком заданного изображения. <xref:System.Drawing.Image> Класс предоставляет <xref:System.Drawing.Image.GetEncoderParameterList%2A> метод, чтобы определить, какие параметров, поддерживаемых для определенного кодировщика. Укажите кодировщика с кодом GUID. <xref:System.Drawing.Image.GetEncoderParameterList%2A> Метод возвращает массив <xref:System.Drawing.Imaging.EncoderParameter> объектов.  
  
## <a name="example"></a>Пример  
 В следующем примере кода выводит параметры, поддерживаемые кодировщиком JPEG. В списке категорий параметров и связанные GUID в <xref:System.Drawing.Imaging.Encoder> Общие сведения о классе для определения категории для каждого параметра.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   приложение Windows Forms;  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Типы растровых изображений](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [Применение кодировщиков и декодеров изображений в управляемом GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
