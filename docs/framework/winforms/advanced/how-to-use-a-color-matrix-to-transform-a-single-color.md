---
title: "Практическое руководство. Использование матрицы цветов для преобразования отдельного цвета"
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
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60da29b60d2b9b5b98c76a0a9c3ae73ac9142bbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>Практическое руководство. Использование матрицы цветов для преобразования отдельного цвета
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]предоставляет <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap> классов для хранения изображений и управления ими. <xref:System.Drawing.Image>и <xref:System.Drawing.Bitmap> объекты хранят цвет каждой точки как 32-разрядное число: 8 бит на красный, зеленый, синий и альфа-канал. Каждый из четырех компонентов — это число от 0 до 255, где 0 соответствует нулевой интенсивности, а 255 — наибольшей интенсивности. Альфа-компонент определяет прозрачность цвета: 0 — полностью прозрачным, а 255 — полностью непрозрачный.  
  
 Цветовой вектор является кортежем в форме (красный, зеленый, синий, альфа-канал). Например цветовой вектор (0, 255, 0, 255) соответствует непрозрачному цвету, не имеет красный и синий, а зеленый полная насыщенность.  
  
 Другое соглашение о представлении цветов использует номер 1 соответствует наибольшей интенсивности. При использовании, описанной в предыдущем абзаце цвет соответствует вектору (0, 1, 0, 1). [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]использует соглашение 1 как максимальная интенсивность при преобразовании цветов.  
  
 Линейные преобразования (поворот, масштабирование и т. д) можно применить к цветовым векторам, умножая эти векторы на матрицу 4 × 4. Однако матрицу 4 × 4 нельзя использовать для выполнения преобразования (нелинейной). Если добавить фиктивную пятую координату (например, номер 1) к каждому из цветовых векторов, можно использовать матрицу 5 × 5 для осуществления любого сочетания линейных преобразований и переводы. Преобразование, состоящее из линейного преобразования и сдвиг называется аффинные преобразования.  
  
 Например предположим, что вы хотите начать с цвета (0,2, 0,0, 0,4, 1.0) и применить следующие преобразования:  
  
1.  Double красного компонента  
  
2.  Добавить 0,2 красного, зеленого и синего компонентов  
  
 Следующие умножение матриц выполняет эти два преобразования в указанном порядке.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")  
  
 Элементы матрицы цветов индексируются (начиная с нуля), строк и столбцов. Например элемент в пятой строке и третьем столбце матрицы M обозначается M [4] [2].  
  
 5 × 5 единичная матрица (как показано на следующем рисунке) имеет единицы на диагонали и размерностью. При умножении вектора на единичную матрицу, цвет не изменяется. Для запуска единичной матрицы и внести небольшое изменение, приводящих к желаемому преобразованию является удобным способом создания матрицы преобразования цветов.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")  
  
 Более подробное рассмотрение матрицы и преобразования в разделе [системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняются изображение, только один цвет (0,2, 0,0, 0,4, 1.0), а затем применяется преобразование, описанное выше.  
  
 Ниже показан исходный образ в левой части экрана и преобразованное изображение справа.  
  
 ![Цвета](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")  
  
 Код в следующем примере использует следующие действия для выполнения гамме.  
  
1.  Инициализация <xref:System.Drawing.Imaging.ColorMatrix> объекта.  
  
2.  Создание <xref:System.Drawing.Imaging.ImageAttributes> и передать <xref:System.Drawing.Imaging.ColorMatrix> объект <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> метод <xref:System.Drawing.Imaging.ImageAttributes> объекта.  
  
3.  Передайте <xref:System.Drawing.Imaging.ImageAttributes> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 [перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
