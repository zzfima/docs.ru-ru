---
title: Как выполнить Сведение изогнутого пути в строку
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: aa47a655417cdf82d79fb222dc6ff6f6d8c3a947
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601822"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Как выполнить Сведение изогнутого пути в строку
Объект <xref:System.Drawing.Drawing2D.GraphicsPath> объект хранит последовательность, линий и сплайнов Безье. Различные типы кривых (эллипсы, дуги, фундаментальные сплайны) можно добавить в путь, но каждую кривую преобразуется в кривую Безье, перед его сохранением в пути. Спрямление путь заключается в преобразовании всех сплайнов Безье в пути в последовательность прямых линий. Ниже показан путь до и после выравнивания.  
  
 ![Прямые линии и кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>Спрямление контура  
  
-   Вызовите <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> метод <xref:System.Drawing.Drawing2D.GraphicsPath> объекта. <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Метод получает аргумент спрямления, который указывает максимальное расстояние между уплощенный путь и исходный путь.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
