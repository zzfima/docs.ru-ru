---
title: Пошаговое руководство. Изображение линий при помощи элемента управления LineShape (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 5e1a837578aab4b4609a58ffee46406b022b8f97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>Пошаговое руководство. Изображение линий при помощи элемента управления LineShape (Visual Studio)
Можно использовать <xref:Microsoft.VisualBasic.PowerPacks.LineShape> элемента управления для отрисовки горизонтальным, вертикальным или диагональные линии в форме или контейнере, как во время разработки, так и во время выполнения.  
  
 **Примечание** на компьютере могут отображаться другие имена или расположения некоторых пользователей Visual Studio элементы интерфейса в следующих инструкциях. Это зависит от имеющегося выпуска Visual Studio и используемых параметров. Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-line-at-design-time"></a>Чтобы нарисовать линию во время разработки  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.LineShape> управления из **Visual Basic PowerPacks** вкладке **элементов** перетащите на форму или контейнерный элемент управления.  
  
2.  Измените размер и переместить маркеры, чтобы изменить размер и положение строки.  
  
     Можно также изменить размер и расположение линии, изменив `X1`, `X2`, `Y1`, и `Y2` свойства в **свойства** окна.  
  
3.  В **свойства** при необходимости задайте дополнительные свойства например `BorderStyle` или `BorderColor` Чтобы изменить внешний вид линии.  
  
### <a name="to-draw-a-line-at-run-time"></a>Чтобы нарисовать линию во время выполнения  
  
1.  В меню **Проект** щелкните команду **Добавить ссылку**.  
  
2.  В **добавить ссылку** выберите **Microsoft.VisualBasic.PowerPacks.VS**, а затем нажмите кнопку **ОК**.  
  
3.  В **редактор кода**, добавьте `Imports` или `using` инструкции в верхней части модуля:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  Добавьте следующий код в процедуру `Event`:  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [Знакомство с элементами управления Line и Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
