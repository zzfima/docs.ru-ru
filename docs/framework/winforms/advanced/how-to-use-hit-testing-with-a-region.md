---
title: Практическое руководство. Использование проверки попадания с регионом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: a9435724e7674fd196ad70bdfd0ab43808a53058
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709757"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Практическое руководство. Использование проверки попадания с регионом
Проверка попадания предназначена для определения, находится ли курсор над данным объектом, например значок или кнопки.  
  
## <a name="example"></a>Пример  
 В следующем примере создается область креста, являющаяся объединением двух прямоугольников. Предполагается, что переменная `point` содержит расположение последнего щелчка. Код проверяет, является ли `point` находится в регионе креста. Если точка находится в регионе (нажатия), область заполняется непрозрачной красной кистью. В противном случае область заполняется полупрозрачные компоненты Красная кисть.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Region>
- [Области в GDI+](regions-in-gdi.md)
- [Практическое руководство. Используйте задание области отсечения](how-to-use-clipping-with-a-region.md)
