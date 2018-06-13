---
title: Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: a6c08d33682e5e2cc936c3aa6aa109ad3389a367
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532903"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 <xref:System.Windows.Forms.ToolBar> кнопки, могут отображать значки для упрощения идентификации пользователей. Это можно сделать, добавив изображения <xref:System.Windows.Forms.ImageList> компонента и связывание его с <xref:System.Windows.Forms.ToolBar> элемента управления.  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ToolBar> управления и <xref:System.Windows.Forms.ImageList> компонента. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Чтобы задать значок для кнопки панели инструментов во время разработки  
  
1.  Добавление изображений к <xref:System.Windows.Forms.ImageList> компонента. Дополнительные сведения см. в разделе [как: Добавление и удаление изображений ImageList с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Выберите <xref:System.Windows.Forms.ToolBar> элемент управления в форме.  
  
3.  В **свойства** задайте <xref:System.Windows.Forms.ToolBar> элемента управления <xref:System.Windows.Forms.ToolBar.ImageList%2A> свойства <xref:System.Windows.Forms.ImageList> компонента.  
  
4.  Нажмите кнопку <xref:System.Windows.Forms.ToolBar> элемента управления <xref:System.Windows.Forms.ToolBar.Buttons%2A> свойство, чтобы выбрать ее и нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **Редактора коллекции**.  
  
5.  Используйте **добавить** кнопку, чтобы добавить кнопки для <xref:System.Windows.Forms.ToolBar> элемента управления.  
  
6.  В **свойства** окно, которое появляется в области справа от **редактора коллекции**, задайте <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> свойства каждой кнопки панели инструментов, одно из значений в списке, который извлекается из изображений, добавленных к <xref:System.Windows.Forms.ImageList> компонента.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolBar>  
 [Практическое руководство. Активация событий меню для кнопок элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
