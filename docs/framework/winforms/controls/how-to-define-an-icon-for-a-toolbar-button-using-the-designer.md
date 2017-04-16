---
title: "Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора | Microsoft Docs"
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
  - "кнопки [Windows Forms], изображения"
  - "примеры [Windows Forms], панели инструментов"
  - "значки [Windows Forms], кнопки панели инструментов"
  - "изображения [Windows Forms], кнопки панели инструментов"
  - "ToolBar - элемент управления [Windows Forms], добавление значков на кнопки"
  - "панели инструментов [Windows Forms], добавление значков на кнопки"
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Для удобства распознавания пользователями кнопки <xref:System.Windows.Forms.ToolBar> способны отображать значки.  Это можно сделать, добавив изображения к компоненту <xref:System.Windows.Forms.ImageList> и связав его с элементом управления <xref:System.Windows.Forms.ToolBar>.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ToolBar> и компонент <xref:System.Windows.Forms.ImageList>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы назначить значок для кнопки на панели инструментов в режиме разработки  
  
1.  Добавьте изображения к компоненту <xref:System.Windows.Forms.ImageList>.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Выберите элемент управления <xref:System.Windows.Forms.ToolBar> в форме.  
  
3.  В окне **Свойства** задайте компоненту <xref:System.Windows.Forms.ImageList> свойство <xref:System.Windows.Forms.ToolBar.ImageList%2A> элемента управления <xref:System.Windows.Forms.ToolBar>.  
  
4.  Щелкните свойство <xref:System.Windows.Forms.ToolBar.Buttons%2A> элемента управления <xref:System.Windows.Forms.ToolBar>, чтобы выбрать его, а затем нажмите кнопку кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), чтобы открыть **Редактор коллекции ToolBarButton**.  
  
5.  Используйте кнопку **Добавить**, чтобы добавить кнопки к элементу управления <xref:System.Windows.Forms.ToolBar>.  
  
6.  В окне **Свойства**, отображаемом на панели справа от **Редактора коллекции ToolBarButton**, для свойства <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> каждой кнопки на панели инструментов укажите одно из значений из списка, составленного на основе изображений, добавленных к компоненту <xref:System.Windows.Forms.ImageList>.  
  
## См. также  
 <xref:System.Windows.Forms.ToolBar>   
 [Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)