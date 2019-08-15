---
title: Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 63692a797ad49f0adc3a0c5b0bfff1aebbc65257
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038265"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора

К <xref:System.Windows.Forms.ImageList> компоненту можно добавлять изображения несколькими разными способами. Вы можете быстро добавлять изображения с помощью смарт-тега <xref:System.Windows.Forms.ImageList>, связанного с, или если вы устанавливаете несколько других свойств <xref:System.Windows.Forms.ImageList>в, может оказаться удобнее добавлять изображения с окно свойств. Можно также добавлять образы с помощью кода. Дополнительные сведения о добавлении изображений с помощью кода см. в разделе [как Добавление или удаление изображений с помощью компонента](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)Windows Forms ImageList. Обычно <xref:System.Windows.Forms.ImageList> компонент заполняется образами, прежде чем он связан с элементом управления, но это не является обязательным.


### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>Добавление или удаление образов с помощью окно свойств

1. <xref:System.Windows.Forms.ImageList> Выберите компонент или добавьте его в форму.

2. В окно свойств нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом <xref:System.Windows.Forms.ImageList.Images%2A> со свойством.

3. В **редакторе коллекции изображений**щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>Добавление или удаление изображений с помощью смарт-тега

1. <xref:System.Windows.Forms.ImageList> Выберите компонент или добавьте его в форму.

2. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")).

3. В диалоговом окне **задачи ImageList** выберите **выбрать изображения**.

4. В **редакторе коллекции изображений** щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.

## <a name="see-also"></a>См. также

- [Изображения, точечные рисунки и метафайлы](../advanced/images-bitmaps-and-metafiles.md)
- [Пошаговое руководство: Выполнение стандартных задач с помощью смарт-тегов в элементах управления Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [Компонент ImageList](imagelist-component-windows-forms.md)
