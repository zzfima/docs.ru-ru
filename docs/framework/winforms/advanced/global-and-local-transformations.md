---
title: Глобальные и локальные преобразования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: a5a8201f0adb44347bdd42081e0263176d179321
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="global-and-local-transformations"></a>Глобальные и локальные преобразования
Глобальные преобразования является преобразование, применяемое ко всем элементам, нарисованная с заданной <xref:System.Drawing.Graphics> объекта. В отличие от этого локального преобразования является преобразование, применяемое к конкретному элементу для отрисовки.  
  
## <a name="global-transformations"></a>Глобальные преобразования  
 Чтобы создать глобальное преобразование, построить <xref:System.Drawing.Graphics> объекта, а затем управлять его <xref:System.Drawing.Graphics.Transform%2A> свойство. <xref:System.Drawing.Graphics.Transform%2A> Свойство <xref:System.Drawing.Drawing2D.Matrix> объекта, поэтому он может содержать любую последовательность аффинных преобразований. Преобразование, заданное <xref:System.Drawing.Graphics.Transform%2A> свойство называется мировое преобразование. <xref:System.Drawing.Graphics> Класс предоставляет несколько методов для построения составного мировое преобразование: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, и <xref:System.Drawing.Graphics.TranslateTransform%2A>. В следующем примере рисуется эллипс дважды: один раз, прежде чем создавать мировое преобразование и один раз после. Преобразование сначала масштабируется с коэффициентом 0,5 по оси y, то преобразует 50 единиц по оси x и поворот на 30 градусов.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 На следующем рисунке изображены матрицы преобразования.  
  
 ![Преобразования](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  В приведенном выше примере поворот эллипса выполняется относительно начала координат, который находится в левом верхнем углу области клиента. Это позволяет создать другой результат, чем поворот эллипса относительно его собственного центра.  
  
## <a name="local-transformations"></a>Локальные преобразования  
 Локальное преобразование применяется к конкретному элементу для отрисовки. Например <xref:System.Drawing.Drawing2D.GraphicsPath> объект имеет <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> метод, который предоставляет возможность преобразовать точки данных этому пути. В следующем примере рисуется прямоугольник без преобразований и путь, содержащий преобразование поворота. (Предполагается, что объемные преобразования отсутствуют.)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Можно объединять мировое преобразование локального преобразования позволяет получать различные результаты. Например можно использовать мировое преобразование для изменения системы координат и использовать локальные преобразования для вращения и масштабирования объектов, рисуемых в новой системе координат.  
  
 Предположим, что нужно задать систему координат с его происхождения 200 пикселей от левого края клиентской области и 150 пикселей от верхнего края клиентской области. Кроме того Предположим, что в единицу измерения должна использоваться точка, ось x вправо, а ось y, указывающая вверх. Система координат по умолчанию имеет ось y направлена вниз, поэтому нужно выполнить отражение относительно горизонтальной оси. На следующем рисунке показана матрица такое отражение.  
  
 ![Преобразования](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 Затем Предположим, что нужно выполнить сдвиг на 200 единиц вправо и на 150 единиц вниз.  
  
 Следующий пример устанавливает системы координат, описанное заданием мировое преобразование объекта <xref:System.Drawing.Graphics> объекта.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Следующий код (он размещен в конце предыдущего примера) создает путь, состоящий из одного прямоугольника, его левого нижнего угла в начале координат новой системы координат. Прямоугольник заливается один раз без применения локальных преобразований и один раз с локального преобразования. Локальное преобразование заключается горизонтального масштабирования с коэффициентом 2, после которого поворот на 30 градусов.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 Ниже показан новый системы координат и двух прямоугольников.  
  
 ![Преобразования](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>См. также  
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Использование преобразований в управляемом GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
