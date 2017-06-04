---
title: "Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], панели инструментов"
  - "ToolBar - элемент управления [Windows Forms], добавление кнопок"
  - "ToolBar - элемент управления [Windows Forms], добавление раскрывающихся меню"
  - "ToolBar - элемент управления [Windows Forms], добавление разделителей"
  - "панели инструментов [Windows Forms], добавление кнопок"
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Неотъемлемой частью элемента управления <xref:System.Windows.Forms.ToolBar> являются добавленные в него кнопки.  Эти кнопки используются для предоставления легкого доступа к командам меню, или их можно разместить в другой области пользовательского интерфейса приложения для представления пользователям команд, недоступных в структуре меню.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ToolBar>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы добавить кнопки во время разработки  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.ToolBar>.  
  
2.  В окне **Свойства** щелкните свойство <xref:System.Windows.Forms.ToolBar.Buttons%2A>, чтобы его выбрать, а затем нажмите кнопку **Ellipsis** \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), чтобы открыть **Редактор коллекции ToolBarButton**.  
  
3.  Используйте кнопки **Добавить** и **Удалить**, чтобы добавить или удалить кнопки из элемента управления <xref:System.Windows.Forms.ToolBar>.  
  
4.  Настройте свойства отдельных кнопок в окне **Свойства**, которое отображается в панели в правой части редактора.  В следующей таблице приведены некоторые важные свойства.  
  
    |Свойство.|Описание|  
    |---------------|--------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Указывает меню, отображаемое кнопкой панели инструментов с раскрывающимся списком.  Для свойства <xref:System.Windows.Forms.ToolBarButton.Style%2A> кнопки панели инструментов необходимо указать значение <xref:System.Windows.Forms.ToolBarButtonStyle>.  Это свойство принимает в качестве ссылки экземпляр класса <xref:System.Windows.Forms.ContextMenu>.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Определяет, находится ли кнопка\-переключатель панели инструментов в частично нажатом состоянии.  Для свойства <xref:System.Windows.Forms.ToolBarButton.Style%2A> кнопки панели инструментов необходимо указать значение <xref:System.Windows.Forms.ToolBarButtonStyle>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Определяет, находится ли кнопка\-переключатель панели инструментов в нажатом состоянии.  Для свойства <xref:System.Windows.Forms.ToolBarButton.Style%2A> кнопки панели инструментов необходимо указать значение <xref:System.Windows.Forms.ToolBarButtonStyle> или <xref:System.Windows.Forms.ToolBarButtonStyle>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Определяет стиль кнопки панели инструментов.  Должен принимать одно из значений из перечисления <xref:System.Windows.Forms.ToolBarButtonStyle>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Текстовая строка, отображаемая кнопкой.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Текст, используемый в качестве всплывающей подсказки для кнопки.|  
  
5.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно и создать указанные панели.  
  
## См. также  
 <xref:System.Windows.Forms.ToolBar>   
 [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Общие сведения об элементе управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)   
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)