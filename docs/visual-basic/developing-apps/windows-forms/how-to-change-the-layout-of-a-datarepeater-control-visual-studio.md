---
title: Как выполнить Изменение макета элемента управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: 3389daa6383444b48faab4c5383b281e44349bce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625605"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>Как выполнить Изменение макета элемента управления DataRepeater (Visual Studio)
<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Элемента управления, которые могут отображаться в горизонтально (элементы прокрутки по горизонтали) или вертикально (элементы прокрутки по вертикали) ориентации. Вы можете изменить ориентацию во время разработки или во время выполнения, изменив <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойство. При изменении <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойство во время выполнения, можно также изменить размер <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и положение дочерних элементов управления.  
  
> [!NOTE]
>  При перемещении элементов управления на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> во время выполнения, необходимо вызвать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> методы в начале и в конце блока кода, изменяются положения элементов управления.  
  
### <a name="to-change-the-layout-at-design-time"></a>Изменение макета во время разработки  
  
1.  В конструкторе Windows Forms выберите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
    > [!NOTE]
    >  Необходимо выбрать внешней границы элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления, щелкнув в нижней области элемента управления, не в верхнем <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> регион.  
  
2.  В окне «Свойства» задайте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> или <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.  
  
### <a name="to-change-the-layout-at-run-time"></a>Изменение макета во время выполнения  
  
1.  Добавьте следующий код для кнопки или меню `Click` обработчик событий:  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  В большинстве случаев требуется добавить код, как описано в разделе "Пример" для изменения размера <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и упорядочивание элементов управления в соответствии с новой ориентации.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реагировать на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> события в обработчик событий. В этом примере требуется наличие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления с именем `DataRepeater1` в форме и его <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> содержат два <xref:System.Windows.Forms.TextBox> элементов управления с именем `TextBox1` и `TextBox2`.  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
