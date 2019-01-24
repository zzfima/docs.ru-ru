---
title: Как выполнить Разрешение переходов между фигурами (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
ms.openlocfilehash: c47d94317008af57907b747e53bd13ae7ca229f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498285"
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a>Как выполнить Разрешение переходов между фигурами (Visual Studio)
Элементы управления Line и shape не имеют `TabStop` или `TabIndex` свойства, но вы по-прежнему можно включить переход между ними. В следующем примере нажав клавишу CTRL и клавиша TAB будет переходов между фигурами; Нажатие клавиши TAB только приведет к переключению между кнопками.  
  
> [!NOTE]
>  Отображаемые на компьютере имена или расположения некоторых элементов пользовательского интерфейса Visual Studio могут отличаться от указанных в следующих инструкциях. Это зависит от имеющегося выпуска Visual Studio и используемых параметров. Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="to-enable-tabbing-among-shapes"></a>Чтобы разрешить переключение между фигурами  
  
1.  Перетащите три <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> элементов управления и два <xref:System.Windows.Forms.Button> управляет из **элементов** в форму.  
  
2.  В **редактор кода**, добавьте `Imports` или `using` инструкция в верхней части модуля:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  Добавьте следующий код в процедуру обработки события:  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  Добавьте следующий код в `Button1_PreviewKeyDown` процедуру обработки события:  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Рисование фигур при помощи OvalShape и RectangleShape элементов управления](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
- [Практическое руководство. Рисование линий с помощью элемента управления LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
- [Знакомство с элементами управления Line и Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
