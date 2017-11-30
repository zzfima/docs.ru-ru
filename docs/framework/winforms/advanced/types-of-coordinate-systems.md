---
title: "Типы систем координат"
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
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be89584ee8e7a82c405bf8664bfad18ced6d989a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-coordinate-systems"></a>Типы систем координат
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]использует три координатных пространства: мировое, страницы и устройства. Мировых координатах являются координаты, используемые для моделирования определенного графического мира и которые можно передать методу в .NET Framework. Страничные координаты система координат, используемая на поверхности, таких как формы или элемента управления. Координаты устройства — координат, используемая отрисовывается, таких как экран или листе физического устройства. При вызове `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, точки, которые вы передаете в <xref:System.Drawing.Graphics.DrawLine%2A> метод —`(0, 0)` и `(160, 80)`— в мировом пространстве координат. Прежде чем [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно нарисовать линию на экране, координаты подвергнутся последовательности преобразований. Преобразует одно преобразование, вызывается мировое преобразование мировых координатах страничных координат и еще одно преобразование, страничное преобразование переводит страничные координаты в координаты устройства.  
  
## <a name="transforms-and-coordinate-systems"></a>Системы координат и преобразования  
 Предположим, что вы хотите работать с системы координат, который расположен в основной части клиентской области, а не в левом верхнем углу. Пусть, например, требуемый источник равным 100 пикселей от левого края клиентской области и 50 пикселей от верхнего края клиентской области. Такая система координат на следующем рисунке.  
  
 ![Система координат](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 При вызове `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, линия, показанные на следующем рисунке.  
  
 ![Система координат](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Ниже приведены координаты конечных точек линии в трех пространствах координат.  
  
|||  
|-|-|  
|World|(0, 0) к (160, 80)|  
|Страница|(100, 50) для (260, 130.)|  
|Устройство|(100, 50) для (260, 130.)|  
  
 Обратите внимание, что пространство координат страницы начала координат в левом верхнем углу области клиента. Это будет всегда так. Также Обратите внимание, что, так как единицей измерения является точка, координаты устройства совпадают страничных координат. Если значение единицы измерения, отличные от точек (например, в дюймах), координаты устройства будут отличаться от страничных координат.  
  
 Мировое преобразование, которая сопоставляет мировых координатах для страничных координат, хранится в <xref:System.Drawing.Graphics.Transform%2A> свойство <xref:System.Drawing.Graphics> класса. В приведенном выше примере мировое преобразование является сдвиг на 100 единиц по оси x и 50 единиц по оси y. В следующем примере задается мировое преобразование объекта <xref:System.Drawing.Graphics> объекта и использование этого <xref:System.Drawing.Graphics> объекта, чтобы нарисовать линию, показанный на предыдущем рисунке:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 Преобразование страницы сопоставляет страничных координат координатах устройства. <xref:System.Drawing.Graphics> Класс предоставляет <xref:System.Drawing.Graphics.PageUnit%2A> и <xref:System.Drawing.Graphics.PageScale%2A> свойства для управления преобразование страницы. <xref:System.Drawing.Graphics> Класс также предоставляет два свойства только для чтения, <xref:System.Drawing.Graphics.DpiX%2A> и <xref:System.Drawing.Graphics.DpiY%2A>, для обеспечения возможности проверки горизонтальной и вертикальной точек на дюйм дисплея.  
  
 Можно использовать <xref:System.Drawing.Graphics.PageUnit%2A> свойство <xref:System.Drawing.Graphics> класса для указания единицы измерения, отличной от точки.  
  
> [!NOTE]
>  Не удается задать <xref:System.Drawing.Graphics.PageUnit%2A> свойства <xref:System.Drawing.GraphicsUnit.World>, как это не физическую единицу и вызовет исключение.  
  
 В следующем примере рисуется строку из (0, 0) на (2, 1), где точка (2, 1) — 2 дюйма вправо и 1 дюйм вниз от точки (0, 0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  Если не указать ширину пера, когда пера, приведенном выше примере будет нарисуйте линию, шириной 1 дюйм. Толщина пера можно указать в качестве второго аргумента <xref:System.Drawing.Pen> конструктор:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Если предположить, что устройство отображения содержит 96 точек на дюйм по горизонтали и 96 точек на дюйм по вертикали, строки в предыдущем примере конечные точки имеют следующие координаты в три координатных пространства:  
  
|||  
|-|-|  
|World|(0, 0) на (2, 1)|  
|Страница|(0, 0) на (2, 1)|  
|Устройство|(0, 0, чтобы (192, 96)|  
  
 Обратите внимание, что поскольку источника объемных координат верхнего левого угла клиентской области, страничные координаты таким же, как мировых координатах.  
  
 Можно объединять мировое и страничное преобразования для получения различных эффектов. Например предположим, вы хотите использовать дюймы в качестве единицы измерения и начало координат должно быть 2 дюйма от левого края клиентской области и 1/2 дюйма от верхнего края клиентской области. В следующем примере задается мировое и страничное преобразования из <xref:System.Drawing.Graphics> объекта, а затем выводит строку из (0, 0) на (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 На следующем рисунке линия и система координат.  
  
 ![Система координат](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Если предположить, что устройство отображения содержит 96 точек на дюйм по горизонтали и 96 точек на дюйм по вертикали, строки в предыдущем примере конечные точки имеют следующие координаты в три координатных пространства:  
  
|||  
|-|-|  
|World|(0, 0) на (2, 1)|  
|Страница|(2, 0,5) для (4, 1.5)|  
|Устройство|(192, 48) для (384, 144)|  
  
## <a name="see-also"></a>См. также  
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Матричное представление преобразований](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
