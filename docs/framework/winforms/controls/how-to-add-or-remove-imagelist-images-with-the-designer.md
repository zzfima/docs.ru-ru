---
title: Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: be17d5e6a12824c1c9edc867c99e77a6a1437a36
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658582"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="fc8d5-102">Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="fc8d5-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="fc8d5-103">К <xref:System.Windows.Forms.ImageList> компоненту можно добавлять изображения несколькими разными способами.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="fc8d5-104">Вы можете быстро добавлять изображения с помощью смарт-тега <xref:System.Windows.Forms.ImageList>, связанного с, или если вы устанавливаете несколько других свойств <xref:System.Windows.Forms.ImageList>в, может оказаться удобнее добавлять изображения с окно свойств.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="fc8d5-105">Можно также добавлять образы с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-105">You can also add images by using code.</span></span> <span data-ttu-id="fc8d5-106">Дополнительные сведения о добавлении изображений с помощью кода см. в разделе [как Добавление или удаление изображений с помощью компонента](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)Windows Forms ImageList.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="fc8d5-107">Обычно <xref:System.Windows.Forms.ImageList> компонент заполняется образами, прежде чем он связан с элементом управления, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="fc8d5-108">Добавление или удаление образов с помощью окно свойств</span><span class="sxs-lookup"><span data-stu-id="fc8d5-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="fc8d5-109"><xref:System.Windows.Forms.ImageList> Выберите компонент или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="fc8d5-110">В окно свойств нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом <xref:System.Windows.Forms.ImageList.Images%2A> со свойством.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="fc8d5-111">В **редакторе коллекции изображений**щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="fc8d5-112">Добавление или удаление изображений с помощью смарт-тега</span><span class="sxs-lookup"><span data-stu-id="fc8d5-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="fc8d5-113"><xref:System.Windows.Forms.ImageList> Выберите компонент или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="fc8d5-114">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")).</span><span class="sxs-lookup"><span data-stu-id="fc8d5-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="fc8d5-115">В диалоговом окне **задачи ImageList** выберите **выбрать изображения**.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-115">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="fc8d5-116">В **редакторе коллекции изображений** щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.</span><span class="sxs-lookup"><span data-stu-id="fc8d5-116">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc8d5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fc8d5-117">See also</span></span>

- [<span data-ttu-id="fc8d5-118">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="fc8d5-118">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="fc8d5-119">Пошаговое руководство: Выполнение стандартных задач с помощью смарт-тегов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fc8d5-119">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="fc8d5-120">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="fc8d5-120">ImageList Component</span></span>](imagelist-component-windows-forms.md)
