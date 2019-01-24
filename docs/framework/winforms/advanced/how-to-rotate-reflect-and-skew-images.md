---
title: Как выполнить Поворот, отражение и наклон изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 2150e7797095b88227b499ec5481a3ce521270e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667915"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Как выполнить Поворот, отражение и наклон изображений
Поворот, отражение и наклон образ, указав конечные точки для верхнего левого, правого верхнего и левого нижнего углов исходного изображения. Три конечные точки определяют аффинное преобразование, которое сопоставляет исходное прямоугольное изображение в параллелограмм.  
  
## <a name="example"></a>Пример  
 Предположим, например, исходный образ представляет собой прямоугольник с верхнего левого угла в (0, 0), правом верхнем углу на (100, 0) и в левом нижнем углу в (0, 50). Теперь допустим, эти три точки в конечные точки следующим образом.  
  
|Исходная точка|Конечная точка|  
|--------------------|-----------------------|  
|Верхний левый угол (0, 0)|(200, 20)|  
|Верхний правый угол (100, 0)|(110, 100)|  
|Нижний левый угол (0, 50)|(250, 30)|  
  
 Ниже показан исходный образ и образ в параллелограмм. Исходное изображение были неравномерным, отражаются, (повернутый) и перевода. Ось x вдоль верхней границы исходного изображения сопоставляется строку, которая выполняется через (200, 20) и (110, 100). Ось y — вдоль левого края исходного изображения сопоставляется строку, которая выполняется через (200, 20) и (250, 30).  
  
 ![Полосы](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 Ниже показано, как преобразование, примененное к фотографии.  
  
 ![Преобразовать Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 Ниже показано, как преобразование, примененное к метафайл.  
  
 ![Преобразовать метафайла](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 В следующем примере создается изображения, показанные на первом рисунке.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий. Не забудьте заменить `Stripes.bmp` с путем к изображению, который действителен в вашей системе.  
  
## <a name="see-also"></a>См. также
- [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
