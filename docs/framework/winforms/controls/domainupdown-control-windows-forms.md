---
title: "Элемент управления DomainUpDown (Windows Forms) | Microsoft Docs"
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
  - "DomainUpDown - элемент управления [Windows Forms]"
  - "счетчик - элемент управления"
  - "счетчик - элемент управления, поля со стрелками "вверх/вниз""
  - "поля со стрелками "вверх/вниз""
  - "поля со стрелками "вверх/вниз", счетчик - элементы управления"
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Элемент управления DomainUpDown (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.DomainUpDown> выглядит как сочетание текстового поля и пары кнопок для перемещения вверх и вниз по списку.  Он выводит и задает текстовую строку в списке вариантов.  Пользователь может выбрать строку, перемещаясь по списку с помощью кнопок со стрелками вверх и вниз, с помощью клавиш со стрелками ВВЕРХ и ВНИЗ или введя строку, совпадающую с элементом в списке.  Один из возможных способов применения этого элемента управления — выбор элементов из списка имен, расположенных в алфавитном порядке.  \(Для сортировки списка свойству <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> необходимо присвоить значение `true`.\) По своему назначению данный элемент управления близок списку или полю со списком, но он более компактен.  
  
 Ключевыми свойствами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.  Свойство <xref:System.Windows.Forms.DomainUpDown.Items%2A> содержит список объектов, текстовые значения которых отображаются в элементе управления.  Если для свойства <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> задано значение `false`, элемент управления автоматически завершает текст, вводимый пользователем, и сопоставляет его со значением в списке.  Если для свойства <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> задано значение `true`, при прокрутке до последнего элемента следом за ним выводится первый элемент списка и наоборот.  Основными методами этого элемента управления являются методы <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Этот элемент управления выводит только текстовые строки.  Для вывода числовых значений следует использовать элемент управления <xref:System.Windows.Forms.NumericUpDown>.  Дополнительные сведения см. в разделе [Элемент управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md).  
  
## В этом подразделе  
 [Общие сведения об элементе управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 Основные понятия, связанные с элементом управления <xref:System.Windows.Forms.DomainUpDown>, который позволяет пользователям просматривать списки текстовых строк и выбирать в них отдельные элементы.  
  
 [Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Описание способов задания текстовых строк, выводимых в элементе управления <xref:System.Windows.Forms.DomainUpDown>.  
  
 [Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Описание способов удаления элементов из элемента управления <xref:System.Windows.Forms.DomainUpDown> в коде.  
  
## Ссылка  
 <xref:System.Windows.Forms.DomainUpDown>  
 Описание класса и ссылки на все его члены.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Описание класса и ссылки на разделы с описанием всех его членов.  
  
## Связанные подразделы  
 [Элементы управления, которые можно использовать в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Полный список элементов управления Windows Forms со ссылками на разделы, в которых описывается их использование.