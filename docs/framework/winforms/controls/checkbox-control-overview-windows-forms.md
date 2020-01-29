---
title: Общие сведения об элементе управления CheckBox
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737092"
---
# <a name="checkbox-control-overview-windows-forms"></a>Общие сведения об элементе управления CheckBox (Windows Forms)
Элемент управления <xref:System.Windows.Forms.CheckBox> Windows Forms указывает, включено или отключено какое-либо условие. Обычно он используется для предоставления пользователю выбора типа "Да/Нет" или "Истина/Ложь". Элементы управления типа "флажок" можно объединять в группы для предоставления нескольких вариантов ответа, из которых пользователь может выбрать один или несколько.  
  
 Элемент управления "флажок" аналогичен элементу управления "переключатель" в том, что каждый из них используется для указания выбора, сделанного пользователем. Они отличаются тем, что в каждый момент времени может быть выбран только один переключатель в группе. Однако при наличии элемента управления "флажок" можно выбрать любое количество флажков.  
  
 Флажок может быть подключен к элементам базы данных с помощью простой привязки данных. Несколько флажков можно сгруппировать с помощью элемента управления <xref:System.Windows.Forms.GroupBox>. Это полезно для визуального отображения, а также для разработки пользовательского интерфейса, так как сгруппированные элементы управления можно перемещать вместе в конструкторе форм. Дополнительные сведения см. в разделе [Windows Forms привязка данных](../windows-forms-data-binding.md) и [элемент управления GroupBox](groupbox-control-windows-forms.md).  
  
 Элемент управления <xref:System.Windows.Forms.CheckBox> имеет два важных свойства: <xref:System.Windows.Forms.CheckBox.Checked%2A> и <xref:System.Windows.Forms.CheckBox.CheckState%2A>. Свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> возвращает либо `true`, либо `false`. Свойство <xref:System.Windows.Forms.CheckBox.CheckState%2A> возвращает либо <xref:System.Windows.Forms.CheckState.Checked>, либо <xref:System.Windows.Forms.CheckState.Unchecked>; или, если свойство <xref:System.Windows.Forms.CheckBox.ThreeState%2A> имеет значение `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> также может возвращать <xref:System.Windows.Forms.CheckState.Indeterminate>. В неопределенном состоянии поле отображается с серым затененным видом, указывающим, что параметр недоступен.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.CheckBox>
- [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [Элемент управления CheckBox](checkbox-control-windows-forms.md)
