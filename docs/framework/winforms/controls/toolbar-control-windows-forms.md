---
title: "Элемент управления ToolBar (Windows Forms) | Microsoft Docs"
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
  - "ToolBar - элемент управления [Windows Forms]"
  - "панели инструментов [Windows Forms]"
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Элемент управления ToolBar (Windows Forms)
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления `ToolBar` и расширяет его функциональные возможности; однако при необходимости элемент управления `ToolBar` можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления Windows Forms `ToolBar` используется в формах в качестве панели управления, на которой выводится ряд раскрывающихся меню и кнопок с растровыми изображениями, активирующих команды.  То есть щелчок по кнопке на панели инструментов эквивалентен выбору команды в меню.  Для кнопок можно настроить режим поведения кнопок, раскрывающихся меню или разделителей.  Обычно на панели инструментов содержатся кнопки и меню, соответствующие элементам в структуре меню приложения, которые предоставляют быстрый доступ к наиболее часто используемым в приложении функциям и командам.  
  
> [!NOTE]
>  Свойство <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> элемента управления `ToolBar` принимает в качестве ссылки экземпляр класса <xref:System.Windows.Forms.ContextMenu>.  При использовании подобных кнопок на панели инструментов приложения будьте внимательны в выборе передаваемой ссылки, так как это свойство принимает любой объект, наследуемый от класса <xref:System.Windows.Forms.Menu>.  
  
## В этом подразделе  
 [Общие сведения об элементе управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 Общие понятия, связанные с элементом управления `ToolBar`, который позволяет разрабатывать пользовательские панели инструментов.  
  
 [Практическое руководство. Добавление кнопок в элемент управления ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 Описываются способы добавления кнопок в элемент управления `ToolBar`.  
  
 [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 Описываются способы отображения значков на кнопках элемента управления `ToolBar`.  
  
 [Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 Инструкции по написанию кода для определения нажатой пользователем кнопки элемента управления `ToolBar`.  
  
 См. также [Практическое руководство. Определение значка для кнопки на панели инструментов с помощью конструктора](http://msdn.microsoft.com/library/ms233659\(v=vs.110\)), [Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора](http://msdn.microsoft.com/library/ms233650\(v=vs.110\)).  
  
## Ссылка  
 Класс <xref:System.Windows.Forms.ToolBar>  
 Справочная информация о классе и его членах.  
  
## Связанные подразделы  
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Полный список элементов управления Windows Forms со ссылками на разделы с описанием их применения.  
  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 Описываются панели инструментов, на которых можно разместить меню, элементы управления и пользовательские элементы управления в приложениях Windows Forms.