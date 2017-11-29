---
title: "Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ecc0fce00dbef1f5b91aad16f32cb7dd7759ac8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Неотъемлемой частью <xref:System.Windows.Forms.ToolBar> элемент управления является кнопок, добавьте к нему. Они используются для обеспечения быстрого доступа к командам меню или, кроме того, их можно разместить в другой области пользовательского интерфейса приложения для представления пользователям, которые недоступны в структуре меню команд.  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ToolBar> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-buttons-at-design-time"></a>Чтобы добавить кнопки во время разработки  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.ToolBar>.  
  
2.  В **свойства** окно, нажмите кнопку <xref:System.Windows.Forms.ToolBar.Buttons%2A> свойство, чтобы выбрать ее и нажмите кнопку **многоточие** (![экрана VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) кнопку, чтобы открыть **редактора коллекции**.  
  
3.  Используйте **добавить** и **удалить** кнопки, чтобы добавить или удалить кнопки из <xref:System.Windows.Forms.ToolBar> элемента управления.  
  
4.  Настройте свойства отдельных кнопок в **свойства** окно, которое появляется в области в правой части редактора. В следующей таблице показаны некоторые важные свойства.  
  
    |Свойство|Описание|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Задает меню, отображаемое на кнопке панели инструментов, раскрывающийся список. Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству необходимо присвоить значение <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>. Это свойство принимает экземпляр <xref:System.Windows.Forms.ContextMenu> класса в качестве ссылки.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Задает ли кнопка-переключатель в нейтральном положении. Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству необходимо присвоить значение <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Задает, является ли кнопка-переключатель в данный момент в нажатом состоянии. Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству необходимо присвоить значение <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> или <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Задает стиль кнопки панели инструментов. Должно быть одно из значений в <xref:System.Windows.Forms.ToolBarButtonStyle> перечисления.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Текстовая строка, отображающийся на кнопке.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Текст, отображаемый в виде всплывающей подсказки для кнопки.|  
  
5.  Нажмите кнопку **ОК** закрыть диалоговое окно и создать указанное панелей.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolBar>  
 [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [Практическое руководство. Активация событий меню для кнопок элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [Общие сведения об элементе управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
