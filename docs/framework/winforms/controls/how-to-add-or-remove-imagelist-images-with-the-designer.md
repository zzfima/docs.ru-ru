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
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора

Изображения можно добавлять в компонент <xref:System.Windows.Forms.ImageList> несколькими разными способами. Вы можете быстро добавлять изображения с помощью смарт-тега, связанного с <xref:System.Windows.Forms.ImageList>, или при установке нескольких других свойств в <xref:System.Windows.Forms.ImageList>может оказаться удобнее добавлять образы с окно свойств. Можно также добавлять образы с помощью кода. Дополнительные сведения о добавлении изображений с помощью кода см. в разделе [как добавлять или удалять изображения с помощью компонента Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md). Как правило, компонент <xref:System.Windows.Forms.ImageList> заполняется образами, прежде чем он связан с элементом управления, но это необязательно.

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>Добавление или удаление образов с помощью окно свойств

1. Выберите компонент <xref:System.Windows.Forms.ImageList> или добавьте его в форму.

2. В окно свойств нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ImageList.Images%2A>.

3. В **редакторе коллекции изображений**щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>Добавление или удаление изображений с помощью смарт-тега

1. Выберите компонент <xref:System.Windows.Forms.ImageList> или добавьте его в форму.

2. Щелкните глиф действия конструктора (![Маленькая черная стрелка](./media/designer-actions-glyph.gif))

3. В диалоговом окне **задачи ImageList** выберите **выбрать изображения**.

4. В **редакторе коллекции изображений** щелкните **Добавить** или **Удалить** , чтобы добавить или удалить изображения из списка.

## <a name="see-also"></a>См. также раздел

- [Изображения, точечные рисунки и метафайлы](../advanced/images-bitmaps-and-metafiles.md)
- [Пошаговое руководство. выполнение стандартных задач с помощью действий конструктора](perform-common-tasks-design-actions.md)
- [Компонент ImageList](imagelist-component-windows-forms.md)
