---
title: "Практическое руководство. Получение списка установленных декодеров"
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
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7993345a39a24c770fdd717580d428968dae836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-list-installed-decoders"></a>Практическое руководство. Получение списка установленных декодеров
Можно перечислить декодеров изображений, доступных на компьютере, для определения, является ли ваше приложение сможет считать определенного файла формата изображений. <xref:System.Drawing.Imaging.ImageCodecInfo> Класс предоставляет <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> статические методы, чтобы определить, какой образ декодеров доступны. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>Возвращает массив <xref:System.Drawing.Imaging.ImageCodecInfo> объектов.  
  
## <a name="example"></a>Пример  
 В следующем примере кода возвращает список установленных декодеров и значения их свойств.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   приложение Windows Forms;  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Получение списка установленных кодировщиков](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Применение кодировщиков и декодеров изображений в управляемом GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
