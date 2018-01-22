---
title: "Практическое руководство. Установка изображения, отображаемого элементом управления Windows Forms, с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
- setting images [Windows Forms], Windows Forms controls
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a31209968957a6d1890cae66c17b74769bd05dc9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="be75d-102">Практическое руководство. Установка изображения, отображаемого элементом управления Windows Forms, с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="be75d-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="be75d-103">Несколько элементов управления Windows Forms можно отображать изображения.</span><span class="sxs-lookup"><span data-stu-id="be75d-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="be75d-104">Изображение может быть значок, поясняющий назначение элемента управления, такие как значок диска на кнопке, отвечающий за **Сохранить** команды.</span><span class="sxs-lookup"><span data-stu-id="be75d-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="be75d-105">Кроме того значок может быть фонового изображения, чтобы предоставить нужный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="be75d-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be75d-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="be75d-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="be75d-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="be75d-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="be75d-108">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="be75d-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="be75d-109">Чтобы задать изображение, отображаемое на элементе управления</span><span class="sxs-lookup"><span data-stu-id="be75d-109">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="be75d-110">В **свойства** выберите **изображения** или **BackgroundImage** свойству элемента управления, затем нажмите кнопку с многоточием ()</span><span class="sxs-lookup"><span data-stu-id="be75d-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     <span data-ttu-id="be75d-111">![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span><span class="sxs-lookup"><span data-stu-id="be75d-111">![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span></span>  
  
     <span data-ttu-id="be75d-112">) для отображения **выберите ресурс** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="be75d-112">) to display the **Select Resource** dialog box.</span></span>  
  
2.  <span data-ttu-id="be75d-113">Выберите изображение, которое нужно отобразить.</span><span class="sxs-lookup"><span data-stu-id="be75d-113">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be75d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="be75d-114">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="be75d-115">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be75d-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
