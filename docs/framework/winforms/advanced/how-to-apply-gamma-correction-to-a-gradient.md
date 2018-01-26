---
title: "Практическое руководство. Применение гамма-коррекции к градиенту"
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
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6321894c86f340154bd37f50e81ea8a58a2e0896
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Практическое руководство. Применение гамма-коррекции к градиенту
Гамма-коррекцию для кисти линейного градиента можно включить, установив кисти <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `true`. Гамма-коррекцию можно отключить, установив <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `false`. Гамма-коррекция отключена по умолчанию.  
  
## <a name="example"></a>Пример  
 В примере создается кисти линейного градиента и используется, для заливки двух прямоугольников. Первый прямоугольник заполняется без гамма-коррекцию, и второй прямоугольник заполняется с гамма-коррекцией.  
  
 На следующем рисунке двух заполненных прямоугольников. Верхний прямоугольник, который не имеет гамма-коррекцию, кажется темным в середине. Дополнительные интенсивность унифицированного появится нижний прямоугольник, имеющая гамма-коррекцию.  
  
 ![Градиент](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [Заливка фигур с помощью градиентной кисти](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
