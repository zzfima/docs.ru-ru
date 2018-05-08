---
title: Практическое руководство. Создание линейного градиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: 9eeedf1ef92bdf6e5e2724eeca5060765b0778f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-linear-gradient"></a>Практическое руководство. Создание линейного градиента
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] поддерживает горизонтальные, вертикальные и диагональные линейные градиенты. По умолчанию цвет в линейном градиенте меняется равномерно. Тем не менее можно настроить линейный градиент, чтобы цвет изменяется таким образом неоднородной.  
  
 В следующем примере заполняется линии, эллипса и прямоугольника с горизонтальной кисти линейного градиента.  
  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Конструктор принимает четыре параметра: две точки и два цвета. Первая точка (0, 10) связан с первый цвет (красный), а вторая точка (200, 10) связан со вторым цветом (синий). Как и следовало ожидать, линии, соединяющей (0, 10) для (200, 10) плавно меняется от красного, синего.  
  
 Вторые точек (50, 10) и (200, 10) не имеют значения. Важно то, что две точки имеют одну координату второй — линию, соединяющую их горизонтальной. Эллипса и прямоугольника тоже плавно меняются от красного, синего как горизонтальной оси находятся значения от 0 до 200.  
  
 На следующем рисунке линии, эллипса и прямоугольника. Обратите внимание, что цветового градиента повторяется заново при увеличении горизонтальной координаты за пределы 200.  
  
 ![Линейный градиент](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>Использование горизонтальных линейных градиентов  
  
-   Передайте непрозрачный красный и непрозрачный синим цветом в качестве третьего и четвертого аргумента соответственно.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 В предыдущем примере цветовые компоненты линейно меняются при перемещении из горизонтальная координата 0 горизонтальная координата 200. Например точки, первая координата на равном расстоянии от 0 до 200 будет синего компонента, который находится на равном расстоянии от 0 до 255.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] позволяет настроить способ цвета при движении от одного края градиент в другой. Предположим, что вы хотите создать градиентной кисти, меняется с черный цвет на красный согласно следующей таблице.  
  
|Горизонтальная координата|RGB-компоненты|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 Обратите внимание, что красный компонент половину интенсивность когда горизонтальная координата составляет только 20 процентов пути от 0 до 200.  
  
 В следующем примере задается <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> свойство <xref:System.Drawing.Drawing2D.LinearGradientBrush> объект, связанный с тремя относительные позиции три относительный интенсивности. Как показано в предыдущей таблице относительная интенсивность 0,5 связан с относительной позиции 0,2. В коде осуществляется заливка эллипса и прямоугольника с градиентной кисти.  
  
 На следующем рисунке окончательный вид эллипса и прямоугольника.  
  
 ![Линейный градиент](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### <a name="to-customize-linear-gradients"></a>Настройка линейных градиентов  
  
-   Передайте непрозрачный черный и непрозрачный красным цветом в качестве третьего и четвертого аргумента соответственно.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 В предыдущих примерах градиенты являлись горизонтальными; то есть цвет плавно меняется при движении вдоль любой горизонтальной линии. Можно также определить вертикальные и диагональные градиенты.  
  
 В следующем примере передается точки (0, 0) и (200, 100), чтобы <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> конструктор. Связан синий цвет (0, 0) и зеленый цвет, связанные с (200, 100). Линия (толщина пера 10) и эллипс заполняются кисти линейного градиента.  
  
 В строке и эллипс на следующем рисунке. Обратите внимание, что цвет эллипса постепенно при движении вдоль любой строке, параллельной прямой, проходящей через (0, 0) и (200, 100).  
  
 ![Линейный градиент](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>Создание диагональных линейных градиентов  
  
-   Передайте непрозрачный синий и непрозрачный зеленым цветом в качестве третьего и четвертого аргумента соответственно.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>См. также  
 [Заливка фигур с помощью градиентной кисти](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
