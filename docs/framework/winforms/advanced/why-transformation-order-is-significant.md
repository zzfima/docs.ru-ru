---
title: Значение порядка преобразований
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 943bfa73b54a1ac5d68d21d2bb6e271133db595a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="why-transformation-order-is-significant"></a>Значение порядка преобразований
Один <xref:System.Drawing.Drawing2D.Matrix> объект может хранить одно преобразование или последовательность преобразований. Называется составное преобразование. Матрица составного преобразования вычисляется путем умножения матриц отдельных преобразований.  
  
## <a name="composite-transform-examples"></a>Примеры составных преобразований  
 Составное преобразование важен порядок отдельных преобразований. Например если сначала сменить, а затем масштабирование, а затем перевести, можно получить другой результат, чем если вы сначала выполнить преобразование, поворот, затем масштабирование. В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], построение составных преобразований слева направо. Если S, R и T матрицы масштабирования, поворота и сдвига соответственно, затем продукта SRT (именно в таком порядке) является матрицей составного преобразования, которое сначала масштабирует, затем поворачивает, а затем преобразует. Матрица произведению SRT отличается от произведением ТС матрицы.  
  
 Одна из причин важен порядок, — что преобразования, как поворот и масштабирование выполняются по отношению к исходной системы координат. Масштабирование объекта, который выравнивается по центру в источнике выдает различный результат, чем масштабирование объекта, который был перемещен этой точки. Аналогично поворот объекта, который выравнивается по центру в источнике выдает различный результат от поворота объекта, который был перемещен этой точки.  
  
 В следующем примере объединяются масштабирования, поворота и преобразования (в указанном порядке) для формирования составного преобразования. Аргумент <xref:System.Drawing.Drawing2D.MatrixOrder.Append> передаваемый <xref:System.Drawing.Graphics.RotateTransform%2A> метод указывает, что поворот будет выполняться после масштабирования. Аналогично аргумент <xref:System.Drawing.Drawing2D.MatrixOrder.Append> передаваемый <xref:System.Drawing.Graphics.TranslateTransform%2A> метод указывает, что сдвиг будет выполняться поворот. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> и <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> являются членами <xref:System.Drawing.Drawing2D.MatrixOrder> перечисления.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 В следующем примере создается те же вызовы методов, как в предыдущем примере, но изменять порядок вызовов. Полученный порядок операций сначала перевести, затем поворот, а затем повернуть шкала, которая дает очень другой результат, масштабирование, затем сдвиг.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Чтобы изменить порядок отдельных преобразований, составное преобразование можно изменить порядок последовательности вызовов метода. Второй способ управления порядком операций является изменение порядка следования матриц. Ниже приведен таким же, как и предыдущий пример, за исключением того, что <xref:System.Drawing.Drawing2D.MatrixOrder.Append> был изменен на <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>. Умножение матриц осуществляется в порядке SRT, где S, R и T являются матрицами масштабирования, поворота и сдвига соответственно. Порядок составного преобразования сначала осуществляется масштабирование, затем поворот, а затем перевести.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 Результат предыдущего примера равен в результате выполнения первого примера в этом разделе. Это так, как были изменены на обратный порядок вызовы методов и порядок умножения матрицы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Использование преобразований в управляемом GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
