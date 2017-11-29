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
ms.openlocfilehash: eee3c8c3f3890054e443f6246b8fa43fd2ef09b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="bd871-102">Практическое руководство. Установка изображения, отображаемого элементом управления Windows Forms, с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="bd871-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="bd871-103">Несколько элементов управления Windows Forms можно отображать изображения.</span><span class="sxs-lookup"><span data-stu-id="bd871-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="bd871-104">Изображение может быть значок, поясняющий назначение элемента управления, такие как значок диска на кнопке, отвечающий за **Сохранить** команды.</span><span class="sxs-lookup"><span data-stu-id="bd871-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="bd871-105">Кроме того значок может быть фонового изображения, чтобы предоставить нужный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bd871-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd871-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="bd871-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bd871-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="bd871-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bd871-108">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="bd871-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="bd871-109">Чтобы задать изображение, отображаемое на элементе управления</span><span class="sxs-lookup"><span data-stu-id="bd871-109">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="bd871-110">В **свойства** выберите **изображения** или **BackgroundImage** свойству элемента управления, затем нажмите кнопку с многоточием ()</span><span class="sxs-lookup"><span data-stu-id="bd871-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     <span data-ttu-id="bd871-111">![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span><span class="sxs-lookup"><span data-stu-id="bd871-111">![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")</span></span>  
  
     <span data-ttu-id="bd871-112">) для отображения **выберите ресурс** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="bd871-112">) to display the **Select Resource** dialog box.</span></span>  
  
2.  <span data-ttu-id="bd871-113">Выберите изображение, которое нужно отобразить.</span><span class="sxs-lookup"><span data-stu-id="bd871-113">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd871-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bd871-114">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="bd871-115">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd871-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
