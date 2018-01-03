---
title: "Пошаговое руководство. Разрешение переходов между фигурами (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0b1e8b0378e65becd80324491632ecd8dbffdbbf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a><span data-ttu-id="dec9a-102">Пошаговое руководство. Разрешение переходов между фигурами (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="dec9a-102">How to: Enable Tabbing Between Shapes (Visual Studio)</span></span>
<span data-ttu-id="dec9a-103">Элементы управления Line и shape не имеют `TabStop` или `TabIndex` свойства, но вы по-прежнему можно включить переход между ними.</span><span class="sxs-lookup"><span data-stu-id="dec9a-103">Line and shape controls do not have `TabStop` or `TabIndex` properties, but you can still enable tabbing among them.</span></span> <span data-ttu-id="dec9a-104">В следующем примере нажав клавишу CTRL и клавиша TAB приведет к переключению между фигурами; Нажатие клавиши TAB только приведет к переключению между кнопками.</span><span class="sxs-lookup"><span data-stu-id="dec9a-104">In the following example, pressing both the CTRL and the TAB keys will tab between shapes; pressing only the TAB key will tab between the buttons.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dec9a-105">Отображаемые на компьютере имена или расположения некоторых элементов пользовательского интерфейса Visual Studio могут отличаться от указанных в следующих инструкциях.</span><span class="sxs-lookup"><span data-stu-id="dec9a-105">Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="dec9a-106">Это зависит от имеющегося выпуска Visual Studio и используемых параметров.</span><span class="sxs-lookup"><span data-stu-id="dec9a-106">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="dec9a-107">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="dec9a-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="to-enable-tabbing-among-shapes"></a><span data-ttu-id="dec9a-108">Чтобы разрешить переключение между фигурами</span><span class="sxs-lookup"><span data-stu-id="dec9a-108">To enable tabbing among shapes</span></span>  
  
1.  <span data-ttu-id="dec9a-109">Перетащите три <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> элементов управления и два <xref:System.Windows.Forms.Button> управляет из **элементов** в форму.</span><span class="sxs-lookup"><span data-stu-id="dec9a-109">Drag three <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls and two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to a form.</span></span>  
  
2.  <span data-ttu-id="dec9a-110">В **редактор кода**, добавьте `Imports` или `using` инструкции в верхней части модуля:</span><span class="sxs-lookup"><span data-stu-id="dec9a-110">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  <span data-ttu-id="dec9a-111">Добавьте следующий код в процедуру обработки события:</span><span class="sxs-lookup"><span data-stu-id="dec9a-111">Add the following code in an event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  <span data-ttu-id="dec9a-112">Добавьте следующий код в `Button1_PreviewKeyDown` процедуру обработки события:</span><span class="sxs-lookup"><span data-stu-id="dec9a-112">Add the following code in the `Button1_PreviewKeyDown` event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dec9a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dec9a-113">See Also</span></span>  
 [<span data-ttu-id="dec9a-114">Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape</span><span class="sxs-lookup"><span data-stu-id="dec9a-114">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [<span data-ttu-id="dec9a-115">Пошаговое руководство. Изображение линий при помощи элемента управления LineShape</span><span class="sxs-lookup"><span data-stu-id="dec9a-115">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [<span data-ttu-id="dec9a-116">Знакомство с элементами управления Line и Shape</span><span class="sxs-lookup"><span data-stu-id="dec9a-116">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
