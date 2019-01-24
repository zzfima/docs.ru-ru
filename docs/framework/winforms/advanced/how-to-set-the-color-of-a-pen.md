---
title: Как выполнить Установка цвета пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: d0402a7d6bb641ef6d97eb41bc25f3c59b3b4250
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569444"
---
# <a name="how-to-set-the-color-of-a-pen"></a>Как выполнить Установка цвета пера
В этом примере изменяется цвет в существующем <xref:System.Drawing.Pen> объекта  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Объект <xref:System.Drawing.Pen> объект с именем `myPen`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Следует вызывать <xref:System.Drawing.Pen.Dispose%2A> на какие объекты используют системные ресурсы (такие как <xref:System.Drawing.Pen> объекты) после завершения их использования.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Pen>
- [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Перья, линии и прямоугольники в GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
