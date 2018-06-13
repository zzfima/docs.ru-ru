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
ms.openlocfilehash: 5b6b5b61b83e5be05999099f2cc6b9e715ca35c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521746"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Практическое руководство. Штриховая заливка фигуры
Шаблон штриховки, состоящее из двух цветов: один для фона и один для строк, формирующих шаблон на фоне. Чтобы залить замкнутую фигуру штриховая, используйте <xref:System.Drawing.Drawing2D.HatchBrush> объекта. Следующий пример демонстрирует Штриховая заливка эллипса:  
  
## <a name="example"></a>Пример  
 <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Конструктор принимает три аргумента: стиль штриховки, цвет штриховой линии и цвет фона. Стиль штриховки может иметь любое значение от <xref:System.Drawing.Drawing2D.HatchStyle> перечисления. Существует более пятидесяти элементов в <xref:System.Drawing.Drawing2D.HatchStyle> перечисления; некоторые из этих элементов приведены в следующем списке:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 На следующем рисунке закрашенный эллипс.  
  
 ![Шаблон штриховки](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
