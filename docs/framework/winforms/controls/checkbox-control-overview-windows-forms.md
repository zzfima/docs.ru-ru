---
title: Общие сведения об элементе управления CheckBox (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: 54a0bba3923626398fb4d1b0af753177dfaa09a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524148"
---
# <a name="checkbox-control-overview-windows-forms"></a>Общие сведения об элементе управления CheckBox (Windows Forms)
Элемент управления <xref:System.Windows.Forms.CheckBox> Windows Forms указывает, включено или отключено какое-либо условие. Обычно он используется для предоставления пользователю выбора типа "Да/Нет" или "Истина/Ложь". Элементы управления типа "флажок" можно объединять в группы для предоставления нескольких вариантов ответа, из которых пользователь может выбрать один или несколько.  
  
 Элемент управления флажком аналогична переключателя в том, что каждый используется для указания выбора, сделанного пользователем. Они отличаются, в которых одновременно можно выбрать только один переключатель в группе. Однако с помощью элемента управления "флажок" любое количество флажки могут быть выбраны.  
  
 Типа "флажок" может быть подключен к элементам в базе данных с помощью простой привязки данных. Несколько флажков объединяются с помощью <xref:System.Windows.Forms.GroupBox> элемента управления. Это полезно для внешнего вида, а также для разработки пользовательского интерфейса, поскольку сгруппированных элементов управления можно перемещать одновременно в конструкторе форм. Дополнительные сведения см. в разделе [привязки данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md) и [управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 <xref:System.Windows.Forms.CheckBox> Управления имеет два важных свойства <xref:System.Windows.Forms.CheckBox.Checked%2A> и <xref:System.Windows.Forms.CheckBox.CheckState%2A>. <xref:System.Windows.Forms.CheckBox.Checked%2A> Свойство возвращает либо `true` или `false`. <xref:System.Windows.Forms.CheckBox.CheckState%2A> Свойство возвращает либо <xref:System.Windows.Forms.CheckState.Checked> или <xref:System.Windows.Forms.CheckState.Unchecked>; или если <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойству `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> могут также возвращать <xref:System.Windows.Forms.CheckState.Indeterminate>. В неопределенном состоянии поле отображается затененным, чтобы указать, что параметр будет недоступен.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.CheckBox>  
 [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [Элемент управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
