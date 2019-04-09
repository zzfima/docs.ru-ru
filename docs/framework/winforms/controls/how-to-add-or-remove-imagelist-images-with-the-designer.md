---
title: Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: b85b4d39235d49966b5f3c108986c8dd04bed5fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161529"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="e09aa-102">Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e09aa-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="e09aa-103">Можно добавить изображения для <xref:System.Windows.Forms.ImageList> компонент несколькими различными способами.</span><span class="sxs-lookup"><span data-stu-id="e09aa-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="e09aa-104">Можно добавлять изображения очень быстро с помощью смарт-тег, связанный с <xref:System.Windows.Forms.ImageList>, или при установке на несколько других свойств <xref:System.Windows.Forms.ImageList>, может оказаться более удобным для добавления изображений в окне "Свойства".</span><span class="sxs-lookup"><span data-stu-id="e09aa-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="e09aa-105">Также можно добавлять изображения с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="e09aa-105">You can also add images by using code.</span></span> <span data-ttu-id="e09aa-106">Дополнительные сведения о способах добавления изображений в коде см. в разделе [как: Добавление и удаление изображений с помощью Windows Forms компонента ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="e09aa-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="e09aa-107">Обычно заполняется <xref:System.Windows.Forms.ImageList> компонент с изображениями, прежде чем он связан с элементом управления, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="e09aa-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e09aa-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="e09aa-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e09aa-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="e09aa-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e09aa-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e09aa-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="e09aa-111">Добавление или удаление изображений с помощью окна свойств</span><span class="sxs-lookup"><span data-stu-id="e09aa-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="e09aa-112">Выберите <xref:System.Windows.Forms.ImageList> компонента, или добавить его в форму.</span><span class="sxs-lookup"><span data-stu-id="e09aa-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="e09aa-113">В окне «Свойства» нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.ImageList.Images%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e09aa-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="e09aa-114">В **редактор коллекции изображений**, нажмите кнопку **добавить** или **удалить** на добавление и удаление изображений из списка.</span><span class="sxs-lookup"><span data-stu-id="e09aa-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="e09aa-115">Добавление и удаление изображений с помощью смарт-тег</span><span class="sxs-lookup"><span data-stu-id="e09aa-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="e09aa-116">Выберите <xref:System.Windows.Forms.ImageList> компонента, или добавить его в форму.</span><span class="sxs-lookup"><span data-stu-id="e09aa-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="e09aa-117">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="e09aa-117">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="e09aa-118">В **задачи ImageList** выберите **выбрать рисунки**.</span><span class="sxs-lookup"><span data-stu-id="e09aa-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="e09aa-119">В **Editor Kolekce Images** щелкните **добавить** или **удалить** на добавление и удаление изображений из списка.</span><span class="sxs-lookup"><span data-stu-id="e09aa-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e09aa-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e09aa-120">See also</span></span>

- [<span data-ttu-id="e09aa-121">Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile</span><span class="sxs-lookup"><span data-stu-id="e09aa-121">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="e09aa-122">Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e09aa-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="e09aa-123">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="e09aa-123">ImageList Component</span></span>](imagelist-component-windows-forms.md)
