---
title: Практическое руководство. Проверка нахождения указателя мыши в заданной области
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 40297fada3d042aee8c317eb787de03662f86cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523095"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Практическое руководство. Проверка нахождения указателя мыши в заданной области
Проверка на наличие предназначено, чтобы определить, является ли курсор над данным объектом, например значок или кнопки.  
  
## <a name="example"></a>Пример  
 В следующем примере создается область креста, являющаяся объединением двух прямоугольников. Предполагается, что переменная `point` содержит положение последнего щелчка. Код проверяет, является ли `point` находится в регионе креста. Если точка находится в области (есть попадание), она закрашивается непрозрачной красной кистью. В противном случае она закрашивается полупрозрачной красной кистью.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Region>  
 [Области в GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [Практическое руководство. Обрезка изображения по границам области обрезки](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
