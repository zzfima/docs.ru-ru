---
title: Общие сведения об элементе управления DomainUpDown (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 21d28caf490b008570cbd6280afff3114b0f4bfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526993"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Общие сведения об элементе управления DomainUpDown (Windows Forms)
Windows Forms <xref:System.Windows.Forms.DomainUpDown> элемент управления является набором текстового поля и пары кнопок для перемещения вверх или вниз по списку. Он выводит и задает текстовую строку в списке вариантов. Пользователь может выбрать строку, щелкнув кнопок со стрелками вверх по списку, клавиши со стрелками вверх и вниз или введя строку, совпадающую с элементом в списке. Того, можно использовать для этого элемента управления можно выбрать элементы из списка имен в алфавитном порядке сортировки.  
  
> [!NOTE]
>  Чтобы отсортировать список, установите <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> свойства `true`.  
  
 Функции данного элемента управления очень похож на список или поле со списком, но оно занимает мало места.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевые свойства элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. <xref:System.Windows.Forms.DomainUpDown.Items%2A> Свойство содержит список объектов, текстовые значения отображаются в элементе управления. Если <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> равно `false`, элемент управления автоматически завершает текст, пользователь и сопоставляет его значение в списке. Если <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> равно `true`, прокручивать за последний элемент перейти к первому элементу в списке и наоборот. Основные методы элемента управления, <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Этот элемент управления отображает только текстовые строки. Если требуется, чтобы элемент управления, отображающий числовые значения, используйте <xref:System.Windows.Forms.NumericUpDown> элемента управления. Дополнительные сведения см. в разделе [Обзор элемента управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DomainUpDown>  
 [Элемент управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
