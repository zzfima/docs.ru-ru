---
title: "Элемент управления DomainUpDown (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 37cec82876edadfed5cda338ca12775ad19ae732
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="domainupdown-control-windows-forms"></a>Элемент управления DomainUpDown (Windows Forms)
Windows Forms <xref:System.Windows.Forms.DomainUpDown> элемент управления выглядит как сочетание текстового поля и пары кнопок для перемещения вверх или вниз по списку. Он выводит и задает текстовую строку в списке вариантов. Пользователь может выбрать строку, щелкнув кнопок со стрелками вверх по списку, клавиши со стрелками вверх и вниз или введя строку, совпадающую с элементом в списке. Того, можно использовать для этого элемента управления можно выбрать элементы из списка имен в алфавитном порядке сортировки. (Чтобы отсортировать список, установите <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> свойства `true`.) Функции данного элемента управления очень похож на список или поле со списком, но оно занимает мало места.  
  
 Ключевые свойства элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. <xref:System.Windows.Forms.DomainUpDown.Items%2A> Свойство содержит список объектов, текстовые значения отображаются в элементе управления. Если <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> равно `false`, элемент управления автоматически завершает текст, пользователь и сопоставляет его значение в списке. Если <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> равно `true`, прокручивать за последний элемент перейти к первому элементу в списке и наоборот. Основные методы элемента управления, <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Этот элемент управления отображает только текстовые строки. Если требуется, чтобы элемент управления, отображающий числовые значения, используйте <xref:System.Windows.Forms.NumericUpDown> элемента управления. Дополнительные сведения см. в разделе [управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>Содержание  
 [Общие сведения об элементе управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 Основные понятия <xref:System.Windows.Forms.DomainUpDown> элемента управления, который позволяет пользователям просматривать и выбирать из списка текстовых строк.  
  
 [Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Описание способа указания текстовые строки <xref:System.Windows.Forms.DomainUpDown> элемент управления должен отображать.  
  
 [Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Содержит сведения об удалении элементов из <xref:System.Windows.Forms.DomainUpDown> элемента управления в коде.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.DomainUpDown>  
 Описание класса и ссылки на все его члены.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Описывает данный класс и содержит ссылки на все его члены...  
  
## <a name="related-sections"></a>Связанные разделы  
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Полный список элементов управления Windows Forms со ссылками на информацию об их применении.
