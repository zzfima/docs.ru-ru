---
title: "Общие сведения об элементе управления DomainUpDown (Windows Forms) | Microsoft Docs"
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
  - "DomainUpDown"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DomainUpDown - элемент управления [Windows Forms], сведения об элементе управления DomainUpDown"
  - "счетчик - элемент управления, сведения об элементе управления "счетчик""
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения об элементе управления DomainUpDown (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.DomainUpDown> по сути представляет собой сочетание текстового поля и пары кнопок для перемещения вверх и вниз по списку.  Он выводит и задает текстовую строку в списке вариантов.  Пользователь может выбрать строку, перемещаясь по списку с помощью кнопок со стрелками вверх и вниз, с помощью клавиш со стрелками ВВЕРХ и ВНИЗ или введя строку, совпадающую с элементом в списке.  Один из возможных способов применения этого элемента управления — выбор элементов из списка имен, расположенных в алфавитном порядке.  
  
> [!NOTE]
>  Для сортировки списка свойству <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> необходимо присвоить значение `true`.  
  
 По своему назначению данный элемент управления близок списку или полю со списком, но он более компактен.  
  
## Ключевые свойства  
 Ключевыми свойствами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.  Свойство <xref:System.Windows.Forms.DomainUpDown.Items%2A> содержит список объектов, текстовые значения которых отображаются в элементе управления.  Если для свойства <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> задано значение `false`, элемент управления автоматически завершает текст, вводимый пользователем, и сопоставляет его со значением в списке.  Если для свойства <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> задано значение `true`, при прокрутке до последнего элемента следом за ним выводится первый элемент списка и наоборот.  Основными методами этого элемента управления являются методы <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Этот элемент управления выводит только текстовые строки.  Для вывода числовых значений следует использовать элемент управления <xref:System.Windows.Forms.NumericUpDown>.  Дополнительные сведения см. в разделе [Общие сведения об элементе управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).  
  
## См. также  
 <xref:System.Windows.Forms.DomainUpDown>   
 [Элемент управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)