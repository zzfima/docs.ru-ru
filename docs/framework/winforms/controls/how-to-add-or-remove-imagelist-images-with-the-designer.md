---
title: Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628726"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="077f5-102">Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="077f5-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="077f5-103">Изображения можно добавлять в компонент <xref:System.Windows.Forms.ImageList> несколькими разными способами.</span><span class="sxs-lookup"><span data-stu-id="077f5-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="077f5-104">Вы можете быстро добавлять изображения с помощью смарт-тега, связанного с <xref:System.Windows.Forms.ImageList>, или при установке нескольких других свойств в <xref:System.Windows.Forms.ImageList>может оказаться удобнее добавлять образы с окно свойств.</span><span class="sxs-lookup"><span data-stu-id="077f5-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="077f5-105">Можно также добавлять образы с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="077f5-105">You can also add images by using code.</span></span> <span data-ttu-id="077f5-106">Дополнительные сведения о добавлении изображений с помощью кода см. в разделе [как добавлять или удалять изображения с помощью компонента Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="077f5-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="077f5-107">Как правило, компонент <xref:System.Windows.Forms.ImageList> заполняется образами, прежде чем он связан с элементом управления, но это необязательно.</span><span class="sxs-lookup"><span data-stu-id="077f5-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="077f5-108">Добавление или удаление образов с помощью окно свойств</span><span class="sxs-lookup"><span data-stu-id="077f5-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="077f5-109">Выберите компонент <xref:System.Windows.Forms.ImageList> или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="077f5-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="077f5-110">В окно свойств нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ImageList.Images%2A>.</span><span class="sxs-lookup"><span data-stu-id="077f5-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="077f5-111">В **редакторе коллекции изображений**щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.</span><span class="sxs-lookup"><span data-stu-id="077f5-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="077f5-112">Добавление или удаление изображений с помощью смарт-тега</span><span class="sxs-lookup"><span data-stu-id="077f5-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="077f5-113">Выберите компонент <xref:System.Windows.Forms.ImageList> или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="077f5-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="077f5-114">Щелкните глиф действия конструктора (</span><span class="sxs-lookup"><span data-stu-id="077f5-114">Click the designer actions glyph (</span></span>![Маленькая черная стрелка](./media/designer-actions-glyph.gif)<span data-ttu-id="077f5-116">)</span><span class="sxs-lookup"><span data-stu-id="077f5-116">)</span></span>

3. <span data-ttu-id="077f5-117">В диалоговом окне **задачи ImageList** выберите **выбрать изображения**.</span><span class="sxs-lookup"><span data-stu-id="077f5-117">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="077f5-118">В **редакторе коллекции изображений** щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.</span><span class="sxs-lookup"><span data-stu-id="077f5-118">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="077f5-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="077f5-119">See also</span></span>

- [<span data-ttu-id="077f5-120">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="077f5-120">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="077f5-121">Пошаговое руководство. выполнение стандартных задач с помощью действий конструктора</span><span class="sxs-lookup"><span data-stu-id="077f5-121">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)
- [<span data-ttu-id="077f5-122">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="077f5-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
