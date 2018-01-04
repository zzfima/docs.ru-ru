---
title: "Практическое руководство. Заливка фигуры сплошным цветом"
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
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f016404feeac47c5f77527b8baa68d70742d4763
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>Практическое руководство. Заливка фигуры сплошным цветом
Чтобы заливка фигуры сплошным цветом, создайте <xref:System.Drawing.SolidBrush> , а затем передать, <xref:System.Drawing.SolidBrush> объект в качестве аргумента для одного из методов заливки класса <xref:System.Drawing.Graphics> класса. В следующем примере показано, как заливка эллипса сплошным красным цветом.  
  
## <a name="example"></a>Пример  
 В следующем коде <xref:System.Drawing.SolidBrush.%23ctor%2A> конструктор принимает <xref:System.Drawing.Color> объект в качестве ее единственного аргумента. Значения, используемые <xref:System.Drawing.Color.FromArgb%2A> метод представления альфа, красного, зеленого и синего компонентов цвета. Каждое из этих значений должно быть в диапазоне от 0 до 255. Первое число 255 указывает, цвет — полностью непрозрачный, а второй 255 показывает, что красный компонент имеет полный интенсивность. Два нуля показывают, что зеленый и синий компоненты имеют интенсивность равна 0.  
  
 Четыре цифры (0, 0, 100, 60), передаваемый <xref:System.Drawing.Graphics.FillEllipse%2A> метода укажите расположение и размер эллипса ограничивающего прямоугольника. Прямоугольник имеет верхний левый угол (0, 0), ширина 100, а высота — 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
