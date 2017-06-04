---
title: "Общие сведения об элементе управления Panel (Windows Forms) | Microsoft Docs"
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
  - "Panel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "группирование элементов управления, Panel - элемент управления"
  - "Panel - элемент управления [Windows Forms], об элементе управления Panel"
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения об элементе управления Panel (Windows Forms)
Элементы управления Windows Forms <xref:System.Windows.Forms.Panel> предназначены для объединения в идентифицируемые группы других элементов управления.  Обычно панели используются для разделения формы по функциям.  Например, это может быть бланк заказа, в котором указаны параметры доставки почты, которые используются при доставке в ночное время.  Объединение всех параметров в группу в панели предоставляет пользователю логическую визуальную подсказку.  В режиме разработки все элементы управления можно легко переместить — при перемещении одного элемента управления <xref:System.Windows.Forms.Panel> перемещаются также все входящие в него элементы управления.  Доступ к объединенным в панели элементам управления можно получить с помощью ее свойства <xref:System.Windows.Forms.Control.Controls%2A>.  Это свойство возвращает коллекцию экземпляров <xref:System.Windows.Forms.Control>, поэтому обычно бывает необходимо привести полученный таким образом элемент управления к определенному типу.  
  
## Сравнение элементов управления GroupBox и Panel  
 Элемент управления <xref:System.Windows.Forms.Panel> имеет некоторое сходство с элементом управления <xref:System.Windows.Forms.GroupBox>, однако только у элемента управления <xref:System.Windows.Forms.Panel> могут быть полосы прокрутки, и только элемент управления <xref:System.Windows.Forms.GroupBox> отображает заголовок.  
  
## Ключевые свойства  
 Для отображения полос прокрутки нужно установить для свойства <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> значение `true`.  Можно также настроить внешний вид панели, задав значения для свойств <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A> и <xref:System.Windows.Forms.Panel.BorderStyle%2A>.  Дополнительные сведения о свойствах <xref:System.Windows.Forms.Control.BackColor%2A> и <xref:System.Windows.Forms.Control.BackgroundImage%2A> см. в разделе [Практическое руководство. Задание фона панели](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md).  Свойство <xref:System.Windows.Forms.Panel.BorderStyle%2A> определяет, выделяется ли панель обычной линией \(<xref:System.Windows.Forms.BorderStyle>\), затененной линией \(<xref:System.Windows.Forms.BorderStyle>\) или границы отсутствуют \(<xref:System.Windows.Forms.BorderStyle>\).  
  
## См. также  
 <xref:System.Windows.Forms.Panel>   
 [Элемент управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)   
 [Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)   
 [Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)