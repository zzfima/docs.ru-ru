---
title: Как выполнить Использование проверки попадания с регионом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 1866810b875063271e206da1fe5d6fc06f7b5de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564309"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Как выполнить Использование проверки попадания с регионом
Проверка попадания предназначена для определения, находится ли курсор над данным объектом, например значок или кнопки.  
  
## <a name="example"></a>Пример  
 В следующем примере создается область креста, являющаяся объединением двух прямоугольников. Предполагается, что переменная `point` содержит расположение последнего щелчка. Код проверяет, является ли `point` находится в регионе креста. Если точка находится в регионе (нажатия), область заполняется непрозрачной красной кистью. В противном случае область заполняется полупрозрачные компоненты Красная кисть.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Region>
- [Области в GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [Практическое руководство. Используйте задание области отсечения](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
