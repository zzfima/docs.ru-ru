---
title: Практическое руководство. Изменение структуры элемента управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: fa780ee40171143c17b5bdbda4a97179ed5f2151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>Практическое руководство. Изменение структуры элемента управления DataRepeater (Visual Studio)
<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Управления могут быть отображены в либо вертикально (элементы прокрутки по вертикали), либо горизонтально (элементы прокрутки по горизонтали) ориентации. Вы можете изменить ориентацию во время разработки или во время выполнения, изменив <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойство. При изменении <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойства во время выполнения можно также для изменения размера <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и положение дочерних элементов управления.  
  
> [!NOTE]
>  При перемещении элементов управления на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> во время выполнения, необходимо вызвать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> методы в начале и в конце блока кода, который перемещает элементы управления.  
  
### <a name="to-change-the-layout-at-design-time"></a>Изменение макета во время разработки  
  
1.  В конструкторе Windows Forms выберите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
    > [!NOTE]
    >  Необходимо выбрать внешней границы <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления, щелкнув в нижней области элемента управления, не в правом верхнем <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> области.  
  
2.  В окне свойств задайте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> или <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.  
  
### <a name="to-change-the-layout-at-run-time"></a>Изменение макета во время выполнения  
  
1.  Добавьте следующий код для кнопки или меню `Click` обработчик событий:  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  В большинстве случаев необходимо добавить код, как показано в следующем примере для изменения размера <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и расположение элементов управления в соответствии с новой ориентации.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реагировать на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> событий в обработчике событий. В этом примере требуется наличие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления с именем `DataRepeater1` в форме и его <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> содержат два <xref:System.Windows.Forms.TextBox> элементов управления с именем `TextBox1` и `TextBox2`.  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
