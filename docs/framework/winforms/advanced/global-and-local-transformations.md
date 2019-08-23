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
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955190"
---
# <a name="global-and-local-transformations"></a>Глобальные и локальные преобразования
Глобальное преобразование — это преобразование, которое применяется к каждому элементу, рисуемому <xref:System.Drawing.Graphics> данным объектом. В отличие от этого, локальное преобразование — это преобразование, которое применяется к конкретному рисуемому элементу.  
  
## <a name="global-transformations"></a>Глобальные преобразования  
 Чтобы создать глобальное преобразование, <xref:System.Drawing.Graphics> создайте объект, а затем измените его <xref:System.Drawing.Graphics.Transform%2A> свойство. <xref:System.Drawing.Graphics.Transform%2A> Свойство<xref:System.Drawing.Drawing2D.Matrix> является объектом, поэтому оно может содержать любую последовательность аффинных преобразований. Преобразование, хранящееся в <xref:System.Drawing.Graphics.Transform%2A> свойстве, называется мировым преобразованием. <xref:System.Drawing.Graphics.RotateTransform%2A> <xref:System.Drawing.Graphics.MultiplyTransform%2A> <xref:System.Drawing.Graphics.TranslateTransform%2A> <xref:System.Drawing.Graphics.ScaleTransform%2A>Класс предоставляет несколько методов для создания составного универсального преобразования:,, и. <xref:System.Drawing.Graphics> В следующем примере эллипс рисуется дважды: один раз перед созданием универсального преобразования и после. Преобразование сначала масштабируется с коэффициента 0,5 в направлении по оси y, затем преобразует 50 единиц в направлении x, а затем поворачивает на 30 градусов.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 На следующем рисунке показаны матрицы, участвующие в преобразовании.  
  
 ![Преобразования](./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
> В предыдущем примере эллипс поворачивается относительно начала координат системы координат, расположенного в левом верхнем углу клиентской области. Результат будет отличаться от того, на котором вращается эллипс относительно своего центра.  
  
## <a name="local-transformations"></a>Локальные преобразования  
 Локальное преобразование применяется к конкретному рисуемому элементу. Например, <xref:System.Drawing.Drawing2D.GraphicsPath> объект <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> имеет метод, позволяющий преобразовывать точки данных этого пути. В следующем примере демонстрируется рисование прямоугольника без преобразования и контура с преобразованием «вращение». (Предположим, что нет универсального преобразования.)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Можно сочетать преобразование «мир» с локальными преобразованиями для получения различных результатов. Например, можно использовать преобразование «мир» для изменения системы координат и использования локальных преобразований для вращения и масштабирования объектов, рисуемых в новой системе координат.  
  
 Предположим, что требуется система координат с координатами 200 пикселей от левого края клиентской области и 150 пикселей от верхней части клиентской области. Кроме того, предположим, что вы хотите, чтобы единица измерения была в пикселе, ось x указывала вправо, а ось y направлена вверх. В системе координат по умолчанию ось y направлена вниз, поэтому необходимо выполнить отражение по горизонтальной оси. На следующем рисунке показана матрица такого отражения.  
  
 ![Преобразования](./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 Затем предположим, что вам нужно выполнить перевод единиц измерения 200 в правый и 150 единиц.  
  
 В следующем примере создается система координат, только что описанная заданием универсального преобразования <xref:System.Drawing.Graphics> объекта.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Следующий код (помещенный в конце предыдущего примера) создает путь, состоящий из одного прямоугольника с нижним левым углом в источнике новой системы координат. Прямоугольник заполняется один раз без локального преобразования и один раз с локальным преобразованием. Локальное преобразование состоит из горизонтального масштабирования с коэффициентом 2, за которым следует поворот на 30 градусов.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 На следующем рисунке показана новая система координат и два прямоугольника.  
  
 ![Преобразования](./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>См. также

- [Системы координат и преобразования](coordinate-systems-and-transformations.md)
- [Использование преобразований в управляемом GDI+](using-transformations-in-managed-gdi.md)
