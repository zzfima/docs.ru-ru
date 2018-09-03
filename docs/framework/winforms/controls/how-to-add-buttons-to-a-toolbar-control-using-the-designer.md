---
title: Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: b96f112c83d2296356e3eb566a24315bcefeff1f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488330"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Неотъемлемой частью <xref:System.Windows.Forms.ToolBar> элемент управления — кнопки, добавьте к нему. Их можно использовать для обеспечения быстрого доступа к командам меню или в качестве альтернативы могут быть размещены в другой области пользовательского интерфейса приложения для представления пользователям, которые не доступны в структуре меню команд.  
  
 Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ToolBar> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-buttons-at-design-time"></a>Чтобы добавить кнопки во время разработки  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.ToolBar>.  
  
2.  В **свойства** окно, нажмите кнопку <xref:System.Windows.Forms.ToolBar.Buttons%2A> свойство, чтобы выбрать ее и нажмите кнопку **кнопку с многоточием** (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) кнопку, чтобы открыть **редактора коллекции**.  
  
3.  Используйте **добавить** и **удалить** кнопки, чтобы добавить или удалить кнопки из <xref:System.Windows.Forms.ToolBar> элемента управления.  
  
4.  Настройте свойства отдельных кнопок в **свойства** окно, которое появляется в области в правой части редактора. В следующей таблице показаны некоторые важные свойства.  
  
    |Свойство.|Описание|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Задает меню, отображаемое кнопкой с раскрывающимся списком. Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству должно быть присвоено <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>. Это свойство принимает экземпляр <xref:System.Windows.Forms.ContextMenu> класс как ссылка.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Задает, является ли кнопка-переключатель в нейтральном положении. Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству должно быть присвоено <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Задает, является ли кнопка-переключатель в данный момент нажата. Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству должно быть присвоено <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> или <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Задает стиль кнопки панели инструментов. Должно быть одно из значений в <xref:System.Windows.Forms.ToolBarButtonStyle> перечисления.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Текстовая строка, отображающийся на кнопке.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Текст, отображаемый в виде всплывающей подсказки для кнопки.|  
  
5.  Нажмите кнопку **ОК** чтобы закрыть диалоговое окно и создать панели, вы указали.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolBar>  
 [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [Практическое руководство. Активация событий меню для кнопок элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [Общие сведения об элементе управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
