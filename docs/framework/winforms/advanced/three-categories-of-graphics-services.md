---
title: "Три категории графических служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53429513426d3b197da4740e5e92d44d8b3a5533
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="three-categories-of-graphics-services"></a>Три категории графических служб
Графические элементы Windows Forms делятся на три основные категории:  
  
-   Двумерные (2-D) векторная графика  
  
-   Создание образа  
  
-   Типографская разметка  
  
## <a name="2-d-vector-graphics"></a>Двумерная векторная графика  
 Создания векторных изображений являются примитивами; Например, линии, кривые линии и фигуры; которые заданы в набором точек в системе координат. Например прямой линии определяется его две конечные точки, а прямоугольник, задаваемый крайними расположение его верхнего левого угла и парой чисел, определяющих высоту и ширину. Простой путь определяется массивом точек, соединенных прямых линий. Сплайн Безье — сложная кривая задана четырьмя контрольными точками.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]предоставляет классы и структуры, хранящие данные о самих примитивах, классы, хранящие данные о способе рисования примитивов и классы, которые фактически не. Например <xref:System.Drawing.Rectangle> структура сохраняет расположение и размер прямоугольника; <xref:System.Drawing.Pen> класс хранит сведения о цвет линий, толщина линии и стиль линии и <xref:System.Drawing.Graphics> класс содержит методы для рисования линии, прямоугольники, путей и другие рисунки. Есть также несколько <xref:System.Drawing.Brush> классы, которые хранят сведения о том, как замкнутых фигур и контуров цветом или рисунком.  
  
 Образ вектор, который представляет последовательность графических команд, можно записать в метафайл. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]предоставляет <xref:System.Drawing.Imaging.Metafile> класс для записи, отображения и сохранения метафайлов. С <xref:System.Drawing.Imaging.MetafileHeader> и <xref:System.Drawing.Imaging.MetaHeader> классов, можно изучить данные, хранимые в заголовке метафайла.  
  
## <a name="imaging"></a>Создание образа  
 Некоторые рисунки сложно или невозможно отображать с использованием векторной графики. Например рисунки на кнопках панели инструментов и изображения, которые отображаются в виде значков сложно указать как коллекции, линий и кривых. С высоким разрешением цифровой фотографии переполненного стадиона еще сложнее помощью векторной. Рисунки такого типа хранятся в виде точечных рисунков — массивов чисел, представляющих цвета точек на экране. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]предоставляет <xref:System.Drawing.Bitmap> класса для отображения, управления и сохранение растровых изображений.  
  
## <a name="typography"></a>Типографская разметка  
 Типографская разметка является отображение текста в разнообразных шрифты, размеры и стили. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]предоставляет расширенную поддержку для этого сложной задачей. Одна из новых функций в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] субточечное сглаживание, позволяющее текст выводится на ЖКИ гладкую внешний.  
  
 Кроме того, Windows Forms предоставляет возможность рисования текста с [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] возможности его <xref:System.Windows.Forms.TextRenderer> класса.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о графике](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [Управляемый код GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [Использование управляемых графических классов](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
