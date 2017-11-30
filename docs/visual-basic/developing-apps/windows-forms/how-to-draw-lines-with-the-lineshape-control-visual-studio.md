---
title: "Пошаговое руководство. Изображение линий при помощи элемента управления LineShape (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f170250dde2f6db31ed68908936c0e9714a7e846
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="432fc-102">Пошаговое руководство. Изображение линий при помощи элемента управления LineShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="432fc-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="432fc-103">Можно использовать <xref:Microsoft.VisualBasic.PowerPacks.LineShape> элемента управления для отрисовки горизонтальным, вертикальным или диагональные линии в форме или контейнере, как во время разработки, так и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="432fc-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="432fc-104">**Примечание** на компьютере могут отображаться другие имена или расположения некоторых пользователей Visual Studio элементы интерфейса в следующих инструкциях.</span><span class="sxs-lookup"><span data-stu-id="432fc-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="432fc-105">Это зависит от имеющегося выпуска Visual Studio и используемых параметров.</span><span class="sxs-lookup"><span data-stu-id="432fc-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="432fc-106">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="432fc-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="432fc-107">Чтобы нарисовать линию во время разработки</span><span class="sxs-lookup"><span data-stu-id="432fc-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="432fc-108">Перетащите <xref:Microsoft.VisualBasic.PowerPacks.LineShape> управления из **Visual Basic PowerPacks** вкладке **элементов** перетащите на форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="432fc-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="432fc-109">Измените размер и переместить маркеры, чтобы изменить размер и положение строки.</span><span class="sxs-lookup"><span data-stu-id="432fc-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="432fc-110">Можно также изменить размер и расположение линии, изменив `X1`, `X2`, `Y1`, и `Y2` свойства в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="432fc-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="432fc-111">В **свойства** при необходимости задайте дополнительные свойства например `BorderStyle` или `BorderColor` Чтобы изменить внешний вид линии.</span><span class="sxs-lookup"><span data-stu-id="432fc-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="432fc-112">Чтобы нарисовать линию во время выполнения</span><span class="sxs-lookup"><span data-stu-id="432fc-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="432fc-113">В меню **Проект** щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="432fc-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="432fc-114">В **добавить ссылку** выберите **Microsoft.VisualBasic.PowerPacks.VS**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="432fc-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="432fc-115">В **редактор кода**, добавьте `Imports` или `using` инструкции в верхней части модуля:</span><span class="sxs-lookup"><span data-stu-id="432fc-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="432fc-116">Добавьте следующий код в процедуру `Event`:</span><span class="sxs-lookup"><span data-stu-id="432fc-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="432fc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="432fc-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="432fc-118">Знакомство с элементами управления Line и Shape</span><span class="sxs-lookup"><span data-stu-id="432fc-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="432fc-119">Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape</span><span class="sxs-lookup"><span data-stu-id="432fc-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
