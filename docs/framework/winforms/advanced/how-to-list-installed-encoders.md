---
title: "Практическое руководство. Получение списка установленных кодировщиков"
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
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70f913acb2620b5c01e1aec1f1eb98b041b82a59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-encoders"></a>Практическое руководство. Получение списка установленных кодировщиков
Можно перечислить кодировщики изображений, доступных на компьютере, для определения ли приложение сохранять в файл формата конкретный образ. <xref:System.Drawing.Imaging.ImageCodecInfo> Класс предоставляет <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> статические методы, чтобы определить, какой образ доступных кодировщиков. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>Возвращает массив <xref:System.Drawing.Imaging.ImageCodecInfo> объектов.  
  
## <a name="example"></a>Пример  
 В следующем примере кода возвращает список установленных кодировщиков и значения их свойств.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   приложение Windows Forms;  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Получение списка установленных декодеров](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [Применение кодировщиков и декодеров изображений в управляемом GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
