---
title: Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: b0018516b9ac337cea3716c4b2eddc6eb859dbb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора
Скрытие пунктов меню — способ управления пользовательского интерфейса (UI) приложения и ограничивать использование команд пользователями. Часто необходимо скрыть меню целиком, когда все элементы меню недоступны. Это меньше отвлекаться для пользователя. Кроме того может потребоваться скрыть и отключить меню или пункта меню, как скрытие не запрещает пользователю доступ к команде меню с помощью сочетания клавиш. Дополнительные сведения об отключении пунктов меню см. в разделе [как: отключение объектов ToolStripMenuItem с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Чтобы скрыть меню верхнего уровня и пунктов подменю  
  
1.  Выберите пункт меню верхнего уровня и задайте его <xref:System.Windows.Forms.ToolStripItem.Visible%2A> или <xref:System.Windows.Forms.ToolStripItem.Available%2A> свойства `false`.  
  
     При скрытии пункт меню верхнего уровня все пункты меню внутри этого меню также скрыты. Если щелкнуть в любом месте за пределами <xref:System.Windows.Forms.MenuStrip> после установки <xref:System.Windows.Forms.ToolStripItem.Visible%2A> для `false`, целиком меню верхнего уровня и пунктов подменю исчезнут из формы, наглядно продемонстрировав результат выполнения этого действия. Для отображения скрытых меню верхнего уровня элемента во время разработки, нажмите кнопку <xref:System.Windows.Forms.MenuStrip> в **область компонентов**в **Структура документа**, или в верхней части сетки свойств.  
  
> [!NOTE]
>  Редко будут скрыты всего меню, за исключением нескольких документа дочерних меню интерфейса MDI в сценарии слияния.  
  
### <a name="to-hide-a-submenu-item"></a>Чтобы скрыть элемент вложенного меню  
  
1.  Выберите элемент вложенного меню и задать его <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства `false`.  
  
     Если скрыть элемент вложенного меню остается видимым в форме во время разработки, то можно легко выделить для дальнейшей работы. Он будет скрыт во время выполнения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
