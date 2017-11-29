---
title: "Практическое руководство. Обрезка изображения по границам области обрезки"
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
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b57ffa91a41900e10aa921bd42509b1288134ff3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-clipping-with-a-region"></a>Практическое руководство. Обрезка изображения по границам области обрезки
Одно из свойств объекта <xref:System.Drawing.Graphics> класс является отсеченную область. Все операции рисования, выполняемые данного <xref:System.Drawing.Graphics> ограничены областью обрезки данного объекта <xref:System.Drawing.Graphics> объекта. Можно задать отсеченную область, вызвав <xref:System.Drawing.Graphics.SetClip%2A> метод.  
  
## <a name="example"></a>Пример  
 В следующем примере создается путь, состоящий из одного многоугольника. Затем код создает область, на основе этого пути. Область передается в <xref:System.Drawing.Graphics.SetClip%2A> метод <xref:System.Drawing.Graphics> рисования объекта и затем двух строк.  
  
 На следующем рисунке обрезанные строки.  
  
 ![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Области в GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [Использование областей](../../../../docs/framework/winforms/advanced/using-regions.md)
