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
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="1ebd0-102">Как выполнить Изменение макета элемента управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="1ebd0-102">How to: Change the Layout of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="1ebd0-103"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Элемента управления, которые могут отображаться в горизонтально (элементы прокрутки по горизонтали) или вертикально (элементы прокрутки по вертикали) ориентации.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-103">The <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control can be displayed in either a vertical (items scroll vertically) or horizontal (items scroll horizontally) orientation.</span></span> <span data-ttu-id="1ebd0-104">Вы можете изменить ориентацию во время разработки или во время выполнения, изменив <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-104">You can change the orientation at design time or at run time by changing the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property.</span></span> <span data-ttu-id="1ebd0-105">При изменении <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойство во время выполнения, можно также изменить размер <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и положение дочерних элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-105">If you change the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property at run time, you may also want to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and reposition the child controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ebd0-106">При перемещении элементов управления на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> во время выполнения, необходимо вызвать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> методы в начале и в конце блока кода, изменяются положения элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-106">If you reposition controls on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> at run time, you will need to call the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> and <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> methods at the beginning and end of the code block that repositions the controls.</span></span>  
  
### <a name="to-change-the-layout-at-design-time"></a><span data-ttu-id="1ebd0-107">Изменение макета во время разработки</span><span class="sxs-lookup"><span data-stu-id="1ebd0-107">To change the layout at design time</span></span>  
  
1.  <span data-ttu-id="1ebd0-108">В конструкторе Windows Forms выберите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ebd0-109">Необходимо выбрать внешней границы элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления, щелкнув в нижней области элемента управления, не в верхнем <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> регион.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-109">You must select the outer border of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control by clicking in the lower region of the control, not in the upper <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> region.</span></span>  
  
2.  <span data-ttu-id="1ebd0-110">В окне «Свойства» задайте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> или <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-110">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property to either <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span></span>  
  
### <a name="to-change-the-layout-at-run-time"></a><span data-ttu-id="1ebd0-111">Изменение макета во время выполнения</span><span class="sxs-lookup"><span data-stu-id="1ebd0-111">To change the layout at run time</span></span>  
  
1.  <span data-ttu-id="1ebd0-112">Добавьте следующий код для кнопки или меню `Click` обработчик событий:</span><span class="sxs-lookup"><span data-stu-id="1ebd0-112">Add the following code to a button or menu `Click` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  <span data-ttu-id="1ebd0-113">В большинстве случаев требуется добавить код, как описано в разделе "Пример" для изменения размера <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и упорядочивание элементов управления в соответствии с новой ориентации.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-113">In most cases, you will want to add code similar to that shown in the Example section to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and rearrange controls to fit the new orientation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ebd0-114">Пример</span><span class="sxs-lookup"><span data-stu-id="1ebd0-114">Example</span></span>  
 <span data-ttu-id="1ebd0-115">В следующем примере показано, как реагировать на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> события в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-115">The following example shows how to respond to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> event in an event handler.</span></span> <span data-ttu-id="1ebd0-116">В этом примере требуется наличие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления с именем `DataRepeater1` в форме и его <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> содержат два <xref:System.Windows.Forms.TextBox> элементов управления с именем `TextBox1` и `TextBox2`.</span><span class="sxs-lookup"><span data-stu-id="1ebd0-116">This example requires that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control named `DataRepeater1` on a form and that its <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contain two <xref:System.Windows.Forms.TextBox> controls named `TextBox1` and `TextBox2`.</span></span>  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1ebd0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1ebd0-117">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [<span data-ttu-id="1ebd0-118">Общие сведения об элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="1ebd0-118">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="1ebd0-119">Устранение неполадок при использовании элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="1ebd0-119">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="1ebd0-120">Практическое руководство. Изменение внешнего вида элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="1ebd0-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
