---
title: "Общие сведения об элементе управления ToolBar (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ToolBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolBar - элемент управления [Windows Forms], сведения об элементах управления ToolBar"
  - "панели инструментов [Windows Forms], сведения о панелях инструментов"
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения об элементе управления ToolBar (Windows Forms)
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления Windows Forms <xref:System.Windows.Forms.ToolBar> используется в формах в качестве панели управления, на которой выводится ряд раскрывающихся меню и кнопок с растровыми изображениями, активизирующими команды.  Таким образом, щелчок кнопки в панели инструментов равносилен выбору команды меню.  Для кнопок можно настроить режим поведения кнопок, раскрывающихся меню или разделителей.  Обычно в панели инструментов содержатся кнопки и меню, соответствующие элементам структуры меню приложения, которые предоставляют быстрый доступ к наиболее часто используемым в приложении функциям и командам.  
  
## Работа с элементом управления ToolBar  
 Элемент управления <xref:System.Windows.Forms.ToolBar> обычно закреплен в верхней части родительского окна, но его можно также закрепить с любой стороны окна.  В панели инструментов могут отображаться подсказки, когда пользователь наводит указатель мыши на кнопку.  Подсказка — это небольшое всплывающее окно с кратким описанием назначения кнопки или меню.  Для отображения всплывающих подсказок нужно установить для свойства <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> значение `true`.  
  
> [!NOTE]
>  В некоторых приложениях представлены элементы управления, очень похожие на панель инструментов; их также можно перемещать в окне приложения.  Для элемента управления Windows Forms ToolBar эти действия недоступны.  
  
 Если свойство <xref:System.Windows.Forms.ToolBar.Appearance%2A> установлено равным [Normal](frlrfSystemWindowsFormsToolBarAppearanceClassTopic), кнопки панели инструментов отображаются приподнятыми и трехмерными.  Задав для свойства <xref:System.Windows.Forms.ToolBar.Appearance%2A> панели инструментов значение <xref:System.Windows.Forms.ToolBarAppearance>, можно отобразить панель инструментов и ее кнопки в плоском виде.  При наведении указателя мыши на плоскую кнопку она становится объемной.  Кнопки панели инструментов можно разделить на логические группы с помощью разделителя.  Разделителем является кнопка панели инструментов, у которой свойство <xref:System.Windows.Forms.ToolBarButton.Style%2A> равно [Separator](frlrfSystemWindowsFormsToolBarButtonStyleClassTopic).  В панели инструментов она отображается в виде пустого места.  В плоской панели инструментов разделители кнопок отображаются в виде линий, разделяющих кнопки, а не в виде промежутков.  
  
 Элемент управления <xref:System.Windows.Forms.ToolBar> позволяет создавать панели инструментов путем добавления объектов <xref:System.Windows.Forms.Button> в коллекцию <xref:System.Windows.Forms.ToolBar.Buttons%2A>.  Можно использовать редактор коллекции для добавления кнопок в элемент управления <xref:System.Windows.Forms.ToolBar>; каждому объекту <xref:System.Windows.Forms.Button> нужно присвоить текст или рисунок, хотя может быть и то, и другое.  Рисунок предоставляется соответствующим компонентом [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md).  Во время выполнения можно добавлять или удалять кнопки с <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> с помощью методов <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> и <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A>.  Для программирования кнопок <xref:System.Windows.Forms.ToolBar> добавьте код в события <xref:System.Windows.Forms.ToolBar.ButtonClick> элемента управления <xref:System.Windows.Forms.ToolBar>, используя свойство <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> класса <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>, чтобы определить, какая кнопка была нажата.  
  
## См. также  
 <xref:System.Windows.Forms.ToolBar>   
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [Практическое руководство. Добавление кнопок в элемент управления ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)   
 [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)