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
ms.locfileid: "33587349"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="16e64-102">Пошаговое руководство. Изображение линий при помощи элемента управления LineShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="16e64-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="16e64-103">Можно использовать <xref:Microsoft.VisualBasic.PowerPacks.LineShape> элемента управления для отрисовки горизонтальным, вертикальным или диагональные линии в форме или контейнере, как во время разработки, так и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="16e64-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="16e64-104">**Примечание** на компьютере могут отображаться другие имена или расположения некоторых пользователей Visual Studio элементы интерфейса в следующих инструкциях.</span><span class="sxs-lookup"><span data-stu-id="16e64-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="16e64-105">Это зависит от имеющегося выпуска Visual Studio и используемых параметров.</span><span class="sxs-lookup"><span data-stu-id="16e64-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="16e64-106">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="16e64-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="16e64-107">Чтобы нарисовать линию во время разработки</span><span class="sxs-lookup"><span data-stu-id="16e64-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="16e64-108">Перетащите <xref:Microsoft.VisualBasic.PowerPacks.LineShape> управления из **Visual Basic PowerPacks** вкладке **элементов** перетащите на форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="16e64-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="16e64-109">Измените размер и переместить маркеры, чтобы изменить размер и положение строки.</span><span class="sxs-lookup"><span data-stu-id="16e64-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="16e64-110">Можно также изменить размер и расположение линии, изменив `X1`, `X2`, `Y1`, и `Y2` свойства в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="16e64-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="16e64-111">В **свойства** при необходимости задайте дополнительные свойства например `BorderStyle` или `BorderColor` Чтобы изменить внешний вид линии.</span><span class="sxs-lookup"><span data-stu-id="16e64-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="16e64-112">Чтобы нарисовать линию во время выполнения</span><span class="sxs-lookup"><span data-stu-id="16e64-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="16e64-113">В меню **Проект** щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="16e64-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="16e64-114">В **добавить ссылку** выберите **Microsoft.VisualBasic.PowerPacks.VS**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="16e64-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="16e64-115">В **редактор кода**, добавьте `Imports` или `using` инструкции в верхней части модуля:</span><span class="sxs-lookup"><span data-stu-id="16e64-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="16e64-116">Добавьте следующий код в процедуру `Event`:</span><span class="sxs-lookup"><span data-stu-id="16e64-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="16e64-117">См. также</span><span class="sxs-lookup"><span data-stu-id="16e64-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="16e64-118">Знакомство с элементами управления Line и Shape</span><span class="sxs-lookup"><span data-stu-id="16e64-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="16e64-119">Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape</span><span class="sxs-lookup"><span data-stu-id="16e64-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
