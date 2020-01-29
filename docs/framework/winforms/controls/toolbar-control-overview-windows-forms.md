---
title: Общие сведения об элементе управления ToolBar
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: f364e052258703331496f8103b48953a90aa3a9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735483"
---
# <a name="toolbar-control-overview-windows-forms"></a>Общие сведения об элементе управления ToolBar (Windows Forms)
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления Windows Forms <xref:System.Windows.Forms.ToolBar> используется в формах в качестве панели управления, на которой выводится ряд раскрывающихся меню и кнопок с растровыми изображениями, активирующих команды. То есть нажатие кнопки на панели инструментов может быть эквивалентно выбору команды в меню. Для кнопок можно настроить режим поведения кнопок, раскрывающихся меню или разделителей. Обычно на панели инструментов содержатся кнопки и меню, соответствующие элементам в структуре меню приложения, которые предоставляют быстрый доступ к наиболее часто используемым в приложении функциям и командам.  
  
## <a name="working-with-the-toolbar-control"></a>Работа с элементом управления ToolBar  
 Элемент управления <xref:System.Windows.Forms.ToolBar> обычно «закреплен» в верхней части родительского окна, но он также может быть прикреплен к любой стороне окна. На панели инструментов могут отображаться подсказки, когда пользователь наводит указатель мыши на кнопку. Всплывающая подсказка представляет собой небольшое всплывающее окно с кратким описанием назначения кнопки или меню. Для вывода всплывающих подсказок свойство <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> должно иметь значение `true`.  
  
> [!NOTE]
> В некоторых приложениях представлены элементы управления, очень похожие на панель инструментов, они могут "плавать" над окном приложения, кроме того, их можно перемещать. Элемент управления панели инструментов Windows Forms не может выполнять такие действия.  
  
 Если свойство <xref:System.Windows.Forms.ToolBar.Appearance%2A> имеет значение <xref:System.Windows.Forms.ToolBarAppearance>, кнопки панели инструментов отображаются и трехмерные. Можно задать для свойства <xref:System.Windows.Forms.ToolBar.Appearance%2A> панели инструментов значение <xref:System.Windows.Forms.ToolBarAppearance>, чтобы панель инструментов и ее кнопки отображались плоскими. При наведении указателя мыши на плоскую кнопку она становится объемной. Кнопки панели инструментов можно разделить на логические группы с помощью разделителя. Разделитель — это кнопка на панели инструментов со свойством <xref:System.Windows.Forms.ToolBarButton.Style%2A>, для которого задано значение <xref:System.Windows.Forms.ToolBarButtonStyle>. Он отображается как пустое место на панели инструментов. Если панель инструментов отображается плоской, разделители кнопок изображаются как линии, а не пустые пространства между кнопками.  
  
 Элемент управления <xref:System.Windows.Forms.ToolBar> позволяет создавать панели инструментов, добавляя <xref:System.Windows.Forms.Button> объекты в коллекцию <xref:System.Windows.Forms.ToolBar.Buttons%2A>. Для добавления кнопок в элемент управления <xref:System.Windows.Forms.ToolBar> можно использовать редактор коллекций. каждому объекту <xref:System.Windows.Forms.Button> должен быть назначен текст или изображение, хотя можно назначить и то, и другое. Изображение предоставляется связанным компонентом [ImageList](imagelist-component-windows-forms.md). Во время выполнения можно добавлять или удалять кнопки из <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> с помощью методов <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> и <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A>. Чтобы программировать кнопки <xref:System.Windows.Forms.ToolBar>, добавьте код в события <xref:System.Windows.Forms.ToolBar.ButtonClick> <xref:System.Windows.Forms.ToolBar>, используя свойство <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> класса <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>, чтобы определить, какая кнопка была нажата.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ToolBar>
- [Элемент управления ToolBar](toolbar-control-windows-forms.md)
- [Практическое руководство. Добавление кнопок в элемент управления ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Практическое руководство. Определение значка для кнопки элемента управления ToolBar](how-to-define-an-icon-for-a-toolbar-button.md)
- [Практическое руководство. Активация событий меню для кнопок элемента управления ToolBar](how-to-trigger-menu-events-for-toolbar-buttons.md)
