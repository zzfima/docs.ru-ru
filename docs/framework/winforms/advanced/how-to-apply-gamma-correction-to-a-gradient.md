---
title: Как выполнить Применение гамма-коррекции к градиенту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: b3b45c312542a3f8410bd93fcbe4e4cb70aa8516
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527163"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Как выполнить Применение гамма-коррекции к градиенту
Гамма-коррекцию для кисти линейного градиента можно включить, задав кисти <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `true`. Гамма-коррекция можно отключить, установив <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `false`. Гамма-коррекция отключена по умолчанию.  
  
## <a name="example"></a>Пример  
 В примере создается кисть линейного градиента и использует этой кисти для заливки двух прямоугольников. Первый прямоугольник заполняется без гамма-коррекции, а второй прямоугольник заполняется гамма-коррекция.  
  
 Ниже показан закрашенный двух прямоугольников. В середине верхним прямоугольником, не имеющем гамма-коррекция, кажется темным. Нижний прямоугольник, который гамма-коррекция, отображается интенсивность дополнительные универсальный код.  
  
 ![Градиента](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [Заливка фигур с помощью градиентной кисти](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
