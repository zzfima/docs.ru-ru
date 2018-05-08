---
title: Практическое руководство. Разработка шрифтов и их семейств
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: ceace5950ec135ea4d52081da7d1de7a820583ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-construct-font-families-and-fonts"></a>Практическое руководство. Разработка шрифтов и их семейств
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] шрифты с же гарнитуры, но разными стилями группируются в семейства шрифтов. Например семейство шрифтов Arial содержит следующие шрифты:  
  
-   Arial обычного  
  
-   Arial полужирным шрифтом  
  
-   Arial курсив  
  
-   Arial полужирный курсив  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] используются четыре стиля для формирования семейств шрифтов: обычный, полужирный, курсив и полужирный курсив. Прилагательные, такие как *сузить* и *округленное* не считаются стили; они являются частями имен семейств шрифтов. Например Arial Narrow — семейство шрифтов с следующие члены:  
  
-   Arial обычного узкий  
  
-   Полужирным шрифтом Arial узкая  
  
-   Arial узких курсив  
  
-   Arial узких полужирный курсив  
  
 Перед тем как выводить текст с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], необходимо создать <xref:System.Drawing.FontFamily> объекта и <xref:System.Drawing.Font> объекта. <xref:System.Drawing.FontFamily> Объекта определяет гарнитуру (например, Arial) и <xref:System.Drawing.Font> объект определяет размер, стиль и единицы измерения.  
  
## <a name="example"></a>Пример  
 В следующем примере создается обычного стиля шрифта Arial с размером 16 пикселей. В следующем коде первый аргумент, переданный <xref:System.Drawing.Font.%23ctor%2A> конструктор является <xref:System.Drawing.FontFamily> объекта. Второй аргумент задает размер шрифта, измеряется в единицах, которые идентифицируют четвертый аргумент. Третий параметр указывает стиль.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> является членом <xref:System.Drawing.GraphicsUnit> перечисления, и <xref:System.Drawing.FontStyle.Regular> является членом <xref:System.Drawing.FontStyle> перечисления.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
