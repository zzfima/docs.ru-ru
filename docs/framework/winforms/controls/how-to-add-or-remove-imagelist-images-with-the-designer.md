---
title: "Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05dd1e06c2cba31bca1282e8d409ab1b5610d1dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="ee5d8-102">Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="ee5d8-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="ee5d8-103">Можно добавить изображения для <xref:System.Windows.Forms.ImageList> компонент несколькими различными способами.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="ee5d8-104">Быстро добавлять рисунки с помощью смарт-тег, связанные с <xref:System.Windows.Forms.ImageList>, или при установке на несколько других свойств <xref:System.Windows.Forms.ImageList>, может оказаться удобнее добавлять изображения с помощью окна «Свойства».</span><span class="sxs-lookup"><span data-stu-id="ee5d8-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="ee5d8-105">Можно также добавлять изображения с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-105">You can also add images by using code.</span></span> <span data-ttu-id="ee5d8-106">Дополнительные сведения о добавлении изображений в коде см. в разделе [как: Добавление и удаление изображений с помощью компонента ImageList в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="ee5d8-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="ee5d8-107">Обычно заполняется <xref:System.Windows.Forms.ImageList> компонент с изображениями, прежде чем он связан с элементом управления, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee5d8-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ee5d8-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="ee5d8-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ee5d8-110">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ee5d8-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="ee5d8-111">Чтобы добавить или удалить изображения с помощью окна «Свойства»</span><span class="sxs-lookup"><span data-stu-id="ee5d8-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="ee5d8-112">Выберите <xref:System.Windows.Forms.ImageList> компонента, или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="ee5d8-113">В окне свойств нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.ImageList.Images%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="ee5d8-114">В **редактор коллекции изображений**, нажмите кнопку **добавить** или **удалить** на добавление и удаление изображений из списка.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="ee5d8-115">Добавление и удаление изображений с помощью смарт-тег</span><span class="sxs-lookup"><span data-stu-id="ee5d8-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="ee5d8-116">Выберите <xref:System.Windows.Forms.ImageList> компонента, или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="ee5d8-117">Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="ee5d8-117">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="ee5d8-118">В **задачи ImageList** выберите **выбрать рисунки**.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="ee5d8-119">В **редактор коллекции изображений** щелкните **добавить** или **удалить** на добавление и удаление изображений из списка.</span><span class="sxs-lookup"><span data-stu-id="ee5d8-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5d8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ee5d8-120">See Also</span></span>  
 [<span data-ttu-id="ee5d8-121">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="ee5d8-121">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="ee5d8-122">Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee5d8-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 [<span data-ttu-id="ee5d8-123">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="ee5d8-123">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
