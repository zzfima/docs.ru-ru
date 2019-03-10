---
title: Практическое руководство. Применение гамма-коррекции к градиенту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e7205058bc2b93ac453b8c37bfc8d5236433158d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708094"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Практическое руководство. Применение гамма-коррекции к градиенту
Гамма-коррекцию для кисти линейного градиента можно включить, задав кисти <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `true`. Гамма-коррекция можно отключить, установив <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `false`. Гамма-коррекция отключена по умолчанию.  
  
## <a name="example"></a>Пример  
 В примере создается кисть линейного градиента и использует этой кисти для заливки двух прямоугольников. Первый прямоугольник заполняется без гамма-коррекции, а второй прямоугольник заполняется гамма-коррекция.  
  
 Ниже показан закрашенный двух прямоугольников. В середине верхним прямоугольником, не имеющем гамма-коррекция, кажется темным. Нижний прямоугольник, который гамма-коррекция, отображается интенсивность дополнительные универсальный код.  
  
 ![Градиента](./media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [Заливка фигур с помощью градиентной кисти](using-a-gradient-brush-to-fill-shapes.md)
