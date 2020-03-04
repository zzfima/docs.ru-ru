---
title: Типы систем координат
ms.date: 03/30/2017
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
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159810"
---
# <a name="types-of-coordinate-systems"></a>Типы систем координат
В GDI+ используются три координатных пространства: мир, страница и устройство. Мировые координаты — это координаты, используемые для моделирования определенного графического мира, а также координаты, передаваемые методам в .NET Framework. Координаты страницы относятся к системе координат, используемой областью рисования, такой как форма или элемент управления. Координаты устройства — это координаты, используемые физическим устройством, которое рисуется, например экран или лист бумаги. При выполнении `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`вызова точки, передаваемые в метод <xref:System.Drawing.Graphics.DrawLine%2A> (`(0, 0)` и `(160, 80)`), находятся в мировом пространстве координат. До того, как интерфейс GDI+ может нарисовать линию на экране, координаты проходят через последовательность преобразований. Одно преобразование, которое называется мировым преобразованием, преобразует мировые координаты в координаты страницы, а другое преобразование, называемое преобразованием страницы, преобразует координаты страницы в координаты устройства.  
  
## <a name="transforms-and-coordinate-systems"></a>Преобразования и системы координат  
 Предположим, что вы хотите работать с системой координат, имеющей свою точку в тексте клиентской области, а не в левом верхнем углу. Предположим, например, что вы хотите, чтобы источник был 100 пикселей от левого края клиентской области и 50 пикселей от верхнего края клиентской области. На следующем рисунке показана такая система координат.  
  
 ![Система координат](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Выполнив вызов `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, вы получаете строку, показанную на следующем рисунке.  
  
 ![Система координат](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Ниже приведены координаты конечных точек линии в трех координатных пространствах.  
  
|||  
|-|-|  
|Реального|(от 0 до 0) до (160, 80)|  
|Страница|(100, 50) в (260, 130)|  
|Устройство|(100, 50) в (260, 130)|  
  
 Обратите внимание, что координатное пространство страницы имеет свой источник в левом верхнем углу клиентской области. Это всегда будет так. Также обратите внимание, что поскольку единицей измерения является пиксель, координаты устройства совпадают с координатами страницы. Если задать для единицы измерения значение, отличное от пикселей (например, дюймы), то координаты устройства будут отличаться от координат на странице.  
  
 Преобразование «мир», которое сопоставляет координаты мира с координатами страницы, хранится в свойстве <xref:System.Drawing.Graphics.Transform%2A> класса <xref:System.Drawing.Graphics>. В предыдущем примере преобразование «мир» представляет собой единицы перевода 100 в направлении x и 50 единиц по оси y. В следующем примере задается универсальное преобразование объекта <xref:System.Drawing.Graphics>, а затем используется этот <xref:System.Drawing.Graphics> объект для отрисовки линии, показанной на предыдущем рисунке:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 Преобразование страницы сопоставляет координаты страницы с координатами устройства. Класс <xref:System.Drawing.Graphics> предоставляет свойства <xref:System.Drawing.Graphics.PageUnit%2A> и <xref:System.Drawing.Graphics.PageScale%2A> для управления преобразованием страницы. Класс <xref:System.Drawing.Graphics> также предоставляет два свойства только для чтения, <xref:System.Drawing.Graphics.DpiX%2A> и <xref:System.Drawing.Graphics.DpiY%2A>, для проверки горизонтальной и вертикальной точек на дюйм устройства дисплея.  
  
 Можно использовать свойство <xref:System.Drawing.Graphics.PageUnit%2A> класса <xref:System.Drawing.Graphics>, чтобы указать единицу измерения, отличную от пикселя.  
  
> [!NOTE]
> Нельзя задать для свойства <xref:System.Drawing.Graphics.PageUnit%2A> значение <xref:System.Drawing.GraphicsUnit.World>, так как это не физическое устройство и вызовет исключение.  
  
 В следующем примере рисуется линия от (0, 0) до (2, 1), где точка (2, 1) — 2 дюйма справа и 1 дюйм вниз от точки (0, 0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> Если вы не укажете толщину пера при создании пера, в предыдущем примере будет нарисована линия шириной в один дюйм. Можно указать ширину пера во втором аргументе в конструкторе <xref:System.Drawing.Pen>:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Если предполагается, что устройство вывода имеет 96 точек на дюйм в горизонтальном направлении и 96 точек на дюйм в вертикальном направлении, конечные точки строки в предыдущем примере имеют следующие координаты в трех координатных пространствах:  
  
|||  
|-|-|  
|Реального|(0, 0) на (2, 1)|  
|Страница|(0, 0) на (2, 1)|  
|Устройство|(от 0 до 0) до (192, 96)|  
  
 Обратите внимание, что поскольку источник пространства координат мира находится в левом верхнем углу клиентской области, координаты страницы совпадают с координатами мира.  
  
 Для получения различных эффектов можно сочетать преобразования «мир» и «страница». Например, предположим, что вы хотите использовать дюйма в качестве единицы измерения и хотите, чтобы источник координат был 2 дюйма от левого края клиентской области и 1/2 дюйма от верхней части клиентской области. В следующем примере задаются преобразование «мир» и «страница» <xref:System.Drawing.Graphics> объекта, после чего рисуется строка от (0, 0) до (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 На следующем рисунке показана линия и система координат.  
  
 ![Система координат](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Если предполагается, что устройство вывода имеет 96 точек на дюйм в горизонтальном направлении и 96 точек на дюйм в вертикальном направлении, конечные точки строки в предыдущем примере имеют следующие координаты в трех координатных пространствах:  
  
|||  
|-|-|  
|Реального|(0, 0) на (2, 1)|  
|Страница|(от 2, 0,5) до (4, 1,5)|  
|Устройство|(192, 48) в (384, 144)|  
  
## <a name="see-also"></a>См. также раздел

- [Системы координат и преобразования](coordinate-systems-and-transformations.md)
- [Матричное представление преобразований](matrix-representation-of-transformations.md)
