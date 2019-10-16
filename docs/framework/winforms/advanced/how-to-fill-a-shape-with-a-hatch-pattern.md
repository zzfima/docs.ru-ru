---
title: Практическое руководство. Штриховая заливка фигуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320054"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Практическое руководство. Штриховая заливка фигуры
Шаблон штриховки состоит из двух цветов: один для фона, а другой для линий, образующих шаблон на фоне. Для заполнения замкнутой фигуры шаблоном штриховки используйте объект <xref:System.Drawing.Drawing2D.HatchBrush>. В следующем примере показано, как заполнить эллипс с помощью шаблона штриховки:  
  
## <a name="example"></a>Пример  
 Конструктор <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> принимает три аргумента: стиль штриховки, цвет линии штриховки и цвет фона. Аргумент стиля штриховки может быть любым значением перечисления <xref:System.Drawing.Drawing2D.HatchStyle>. В перечислении <xref:System.Drawing.Drawing2D.HatchStyle> содержится более 50 элементов; Некоторые из этих элементов показаны в следующем списке:  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 На следующем рисунке показан закрашенный эллипс.  
  
  ![Снимок экрана, как выглядит эллипс с шаблоном штриховки.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также

- [Использование кисти для заливки фигур](using-a-brush-to-fill-shapes.md)
