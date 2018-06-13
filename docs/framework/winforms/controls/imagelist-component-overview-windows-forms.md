---
title: Общие сведения о компоненте ImageList (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
ms.openlocfilehash: bda9bb71dd2e9b6da2de2444013ed724979f61af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535289"
---
# <a name="imagelist-component-overview-windows-forms"></a>Общие сведения о компоненте ImageList (Windows Forms)
Компонент <xref:System.Windows.Forms.ImageList> в Windows Forms используется для хранения изображений, которые затем будут отображаться элементами управления. Список изображений позволяет написать код для создания единого согласованного каталога изображений. Например, можно поворачивать изображения, отображаемые элементом управления <xref:System.Windows.Forms.Button>, просто изменив свойство <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> или <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> кнопки. Кроме того, можно связать один список изображений с несколькими элементами управления. Например, если вы используете оба элемента управления, <xref:System.Windows.Forms.ListView> и <xref:System.Windows.Forms.TreeView>, для отображения одного списка файлов, при изменении значка файла в списке изображений новый значок будет отображаться в обоих представлениях.  
  
## <a name="using-imagelist-with-controls"></a>Использование компонента ImageList с элементами управления  
 Список изображений можно использовать с любым элементом управления, который имеет свойство `ImageList` (или свойства <xref:System.Windows.Forms.ListView.SmallImageList%2A> и <xref:System.Windows.Forms.ListView.LargeImageList%2A>, если используется элемент управления <xref:System.Windows.Forms.ListView>). Элементы управления, которые могут быть связаны со списком изображений, включают: <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.Label>. Чтобы связать список изображений с элементом управления, задайте для свойства `ImageList` элемента управления имя компонента <xref:System.Windows.Forms.ImageList>.  
  
## <a name="key-properties"></a>Основные свойства  
 Основным свойством компонента <xref:System.Windows.Forms.ImageList> является <xref:System.Windows.Forms.ImageList.Images%2A>, которое содержит изображения для использования связанным элементом управления. Доступ к каждому отдельному изображению может осуществляться по значению индекса или ключу. Свойство <xref:System.Windows.Forms.ImageList.ColorDepth%2A> определяет количество цветов, которые используются для отрисовки изображений. Размер всех отображаемых изображений будет одинаковым (задается свойством <xref:System.Windows.Forms.ImageList.ImageSize%2A>). Изображения, размер которых больше заданного, масштабируются.  
  
 При использовании [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] вы получаете доступ к большой библиотеке стандартных изображений, которые можно использовать в приложениях.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ImageList>  
 [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
