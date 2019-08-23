---
title: Общие сведения об элементе управления ToolBar (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: c7c19783963bb315a0356979797c6f4d4e3b9e08
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929597"
---
# <a name="toolbar-control-overview-windows-forms"></a>Общие сведения об элементе управления ToolBar (Windows Forms)
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления Windows Forms <xref:System.Windows.Forms.ToolBar> используется в формах в качестве панели управления, на которой выводится ряд раскрывающихся меню и кнопок с растровыми изображениями, активирующих команды. То есть нажатие кнопки на панели инструментов может быть эквивалентно выбору команды в меню. Для кнопок можно настроить режим поведения кнопок, раскрывающихся меню или разделителей. Обычно на панели инструментов содержатся кнопки и меню, соответствующие элементам в структуре меню приложения, которые предоставляют быстрый доступ к наиболее часто используемым в приложении функциям и командам.  
  
## <a name="working-with-the-toolbar-control"></a>Работа с элементом управления ToolBar  
 <xref:System.Windows.Forms.ToolBar> Элемент управления обычно «закреплен» в верхней части родительского окна, но он также может быть прикреплен к любой стороне окна. На панели инструментов могут отображаться подсказки, когда пользователь наводит указатель мыши на кнопку. Всплывающая подсказка представляет собой небольшое всплывающее окно с кратким описанием назначения кнопки или меню. Для вывода всплывающих подсказок <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> свойство должно иметь `true`значение.  
  
> [!NOTE]
> В некоторых приложениях представлены элементы управления, очень похожие на панель инструментов, они могут "плавать" над окном приложения, кроме того, их можно перемещать. Элемент управления панели инструментов Windows Forms не может выполнять такие действия.  
  
 Если свойство имеет <xref:System.Windows.Forms.ToolBarAppearance>значение, кнопки панели инструментов отображаются и трехмерные. <xref:System.Windows.Forms.ToolBar.Appearance%2A> Можно задать <xref:System.Windows.Forms.ToolBar.Appearance%2A> для <xref:System.Windows.Forms.ToolBarAppearance> свойства панели инструментов значение, чтобы панель инструментов и ее кнопки отображались плоскими. При наведении указателя мыши на плоскую кнопку она становится объемной. Кнопки панели инструментов можно разделить на логические группы с помощью разделителя. Разделитель — это кнопка панели инструментов, свойству которой <xref:System.Windows.Forms.ToolBarButton.Style%2A> <xref:System.Windows.Forms.ToolBarButtonStyle>присвоено значение. Он отображается как пустое место на панели инструментов. Если панель инструментов отображается плоской, разделители кнопок изображаются как линии, а не пустые пространства между кнопками.  
  
 Элемент управления позволяет создавать панели инструментов путем добавления <xref:System.Windows.Forms.Button> объектов в <xref:System.Windows.Forms.ToolBar.Buttons%2A> коллекцию. <xref:System.Windows.Forms.ToolBar> Редактор коллекций можно использовать для добавления кнопок в <xref:System.Windows.Forms.ToolBar> элемент управления; каждому <xref:System.Windows.Forms.Button> объекту должен быть назначен текст или изображение, хотя можно назначить и то, и другое. Изображение предоставляется связанным компонентом [ImageList](imagelist-component-windows-forms.md). Во время выполнения можно добавлять или удалять кнопки из <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> с <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> помощью методов и <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> . <xref:System.Windows.Forms.ToolBar>Чтобы программировать кнопки, добавьте код <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.ButtonClick> в события <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> объекта, используя свойство <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> класса, чтобы определить, какая кнопка была нажата.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolBar>
- [Элемент управления ToolBar](toolbar-control-windows-forms.md)
- [Практическое руководство. Добавление кнопок в элемент управления ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Практическое руководство. Определение значка для кнопки на панели инструментов](how-to-define-an-icon-for-a-toolbar-button.md)
- [Практическое руководство. События меню триггера для кнопок панели инструментов](how-to-trigger-menu-events-for-toolbar-buttons.md)
