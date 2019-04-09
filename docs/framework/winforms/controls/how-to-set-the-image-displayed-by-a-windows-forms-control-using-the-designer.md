---
title: Практическое руководство. Установка изображения, отображаемого элементом управления Windows Forms, с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
- setting images [Windows Forms], Windows Forms controls
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
ms.openlocfilehash: 2e0837e4a3058db7f1086d6a8ed53136ec86c7ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153495"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="ee5bc-102">Практическое руководство. Установка изображения, отображаемого элементом управления Windows Forms, с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="ee5bc-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="ee5bc-103">Несколько элементов управления Windows Forms можно отображать изображения.</span><span class="sxs-lookup"><span data-stu-id="ee5bc-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="ee5bc-104">Изображение может быть значок, поясняющий назначение элемента управления, такие как значок диска на кнопку, обозначающая **Сохранить** команды.</span><span class="sxs-lookup"><span data-stu-id="ee5bc-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="ee5bc-105">Кроме того значок может быть фоновое изображение для предоставления необходимого внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ee5bc-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee5bc-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="ee5bc-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ee5bc-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="ee5bc-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ee5bc-108">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ee5bc-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="ee5bc-109">Чтобы задать изображение, отображаемое элементом управления</span><span class="sxs-lookup"><span data-stu-id="ee5bc-109">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="ee5bc-110">В **свойства** выберите **изображение** или **BackgroundImage** свойство элемента управления, нажмите кнопку с многоточием ()</span><span class="sxs-lookup"><span data-stu-id="ee5bc-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     <span data-ttu-id="ee5bc-111">![Снимок экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")</span><span class="sxs-lookup"><span data-stu-id="ee5bc-111">![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")</span></span>  
  
     <span data-ttu-id="ee5bc-112">) для отображения **Выбор ресурса** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ee5bc-112">) to display the **Select Resource** dialog box.</span></span>  
  
2.  <span data-ttu-id="ee5bc-113">Выберите изображение, которое вы хотите отобразить.</span><span class="sxs-lookup"><span data-stu-id="ee5bc-113">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5bc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ee5bc-114">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="ee5bc-115">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee5bc-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
