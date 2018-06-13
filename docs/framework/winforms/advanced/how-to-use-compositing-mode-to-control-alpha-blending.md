---
title: Практическое руководство. Использование режима комбинирования для управления альфа-смешением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 55c6db1029c6823652ac29fca46f6f8dc4ec40d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527006"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Практическое руководство. Использование режима комбинирования для управления альфа-смешением
Могут возникнуть ситуации, когда требуется создать в битовом изображении, который имеет следующие характеристики:  
  
-   Цвета имеет альфа-значения, которые меньше 255.  
  
-   Не выполняется альфа-смешение цветов друг с другом, как создать точечный рисунок.  
  
-   При отображении готовой растрового изображения, цвета в битовой карте, альфа-смешение цвета фона на устройстве отображения.  
  
 Чтобы создать такой точечный рисунок, создать пустой <xref:System.Drawing.Bitmap> объекта, а затем постройте <xref:System.Drawing.Graphics> объекта на его основе. Установите режим композиции <xref:System.Drawing.Graphics> объект <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Graphics> объекта, основанного на <xref:System.Drawing.Bitmap> объекта. Код использует <xref:System.Drawing.Graphics> вместе с двумя полупрозрачными кистями (альфа = 160) для рисования растрового изображения. В коде осуществляется заливка красного и зеленого эллипсов, с помощью полупрозрачными кистями. Зеленый эллипс частично перекрывается с красным эллипсом, но зеленый и красный значок не смешиваются, потому что режим комбинирования <xref:System.Drawing.Graphics> , присваивается значение <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 Точечный рисунок рисуется на экране дважды: один раз на белом фоне и один раз на многоцветном фоне. Точки в битовой карте, являющиеся частью двух эллипсов имеют альфа-компонент, равный 160, поэтому цвета эллипсов смешиваются с фоновыми цветами на экране.  
  
 Ниже показан результат выполнения примера кода. Обратите внимание, что цвета эллипсов смешиваются с фоном, но не смешиваются друг с другом.  
  
 ![Источник копирования](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 Пример кода содержит следующую инструкцию:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Если требуется эллипсов смешивались друг с другом, а также с цветом фона, измените этот оператор следующим образом:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 Ниже показан результат выполнения измененного кода.  
  
 ![Источник над](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Альфа-смешение цвета для линий и заливок](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
