---
title: "Глобальные и локальные преобразования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "матрицы, использование преобразований"
  - "преобразования, общие"
  - "преобразования, локальные"
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Глобальные и локальные преобразования
Глобальными преобразованиями называются преобразования, которые применяются ко всем элементам, нарисованным с помощью данного объекта <xref:System.Drawing.Graphics>.  Локальным преобразованием называется преобразование, применяемое к определенному рисуемому элементу.  
  
## Глобальные преобразования  
 Чтобы создать глобальное преобразование, нужно создать объект <xref:System.Drawing.Graphics> и нужным образом изменить значение его свойства <xref:System.Drawing.Graphics.Transform%2A>.  Значением свойства <xref:System.Drawing.Graphics.Transform%2A> является объект <xref:System.Drawing.Drawing2D.Matrix>, который может содержать любую последовательность аффинных преобразований.  Преобразование, заданное свойством <xref:System.Drawing.Graphics.Transform%2A>, называется объемным преобразование.  Класс <xref:System.Drawing.Graphics> содержит несколько методов, осуществляющих составные объемные преобразования: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A> и <xref:System.Drawing.Graphics.TranslateTransform%2A>.  В приведенном ниже примере дважды демонстрируется рисование эллипса: один раз перед заданием объемных преобразований и один раз после.  Преобразование заключается в масштабировании вдоль оси Y с масштабным коэффициентом 0,5, после которого выполняется сдвиг на 50 единиц по оси X, а затем выполняется поворот на 30 градусов.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 На приведенном ниже рисунке изображены использовавшиеся при задании преобразования матрицы.  
  
 ![Преобразования](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.png "AboutGdip05\_art14")  
  
> [!NOTE]
>  В приведенном выше примере поворот эллипса выполняется относительно расположенного в верхнем левом углу клиентской области начала координат.  Результат применения такого поворота отличается от поворота эллипса относительно его собственного центра.  
  
## Локальные преобразования  
 Локальным преобразованием называется преобразование, применяемое к определенному рисуемому элементу.  Например, объект <xref:System.Drawing.Drawing2D.GraphicsPath> содержит метод <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A>, позволяющий выполнять преобразования над точками, задающими контур.  В приведенном ниже примере демонстрируется рисование прямоугольника без преобразования и рисование контура с применением поворота.  \(Предполагается, что объемные преобразования отсутствуют.\)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Сочетание объемного преобразования и локального преобразования позволяет получать различные результаты.  Например, объемное преобразование можно использовать для изменения системы координат, а локальные преобразования можно использовать для вращения и масштабирования объектов, рисуемых в новой системе координат.  
  
 Предположим, что нужно задать систему координат с началом, удаленным на 200 пикселей от левого края и на 150 пикселей от верхнего края клиентской области.  Кроме того, предположим, что в качестве единицы измерения в этой системе координат должен использоваться пиксель, ось X должна быть направлена вправо, а ось Y — вверх.  Ось Y системы координат, заданной по умолчанию, направлена вниз, поэтому нужно выполнить отражение относительно горизонтальной оси.  На приведенном ниже рисунке показана матрица, задающая такое отражение.  
  
 ![Преобразования](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.png "AboutGdip05\_art15")  
  
 Затем предположим, что нужно выполнить сдвиг на 200 единиц вправо и на 150 единиц вниз.  
  
 В приведенном ниже примере демонстрируется введение системы координат, описанное заданием объемного преобразования для объекта <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Приведенный ниже код \(который должен следовать сразу после кода из примера, приведенного выше\) создает контур, состоящий из одного прямоугольника, нижний левый угол которого расположен в начале новой системы координат.  Прямоугольник заливается один раз без применения локальных преобразований и один раз с применением локального преобразования.  Локальное преобразование заключается в масштабировании по горизонтали с коэффициентом 2, после которого применяется поворот на 30 градусов.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 На приведенном ниже рисунке изображена полученная новая система координат и два прямоугольника.  
  
 ![Преобразования](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.png "AboutGdip05\_art16")  
  
## См. также  
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Использование преобразований в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)