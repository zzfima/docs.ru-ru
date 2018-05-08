---
title: Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: cbc6ab410fa2ab9d89255f82863e51aad36f8c18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms
Windows Forms <xref:System.Windows.Forms.RadioButton> элементы управления предназначены для предоставления пользователям выбора между двумя или несколькими параметрами, из которых только один присвоен процедуре или объекту. Например, группу <xref:System.Windows.Forms.RadioButton> элементов управления может отображать выбор способа доставки заказа, но только один способ будет использоваться. Поэтому только один <xref:System.Windows.Forms.RadioButton> одновременно можно выбрать, даже если он является частью функциональной группы.  
  
 Группы переключателей путем их рисования внутри контейнеров, таких как <xref:System.Windows.Forms.Panel> управления <xref:System.Windows.Forms.GroupBox> управления или формы. Все переключатели, добавленные непосредственно для одной группы становятся формы. Для добавления отдельных групп следует разместить их внутри элементов управления или групп. Дополнительные сведения о панелях и группах см. в разделе [Обзор элемента управления панели](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) или [Обзор элемента управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Чтобы сгруппировать элементы управления RadioButton как набор для функционирования независимо от других наборов  
  
1.  Перетащите <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel> управления из **Windows Forms** на вкладке **элементов** в форму.  
  
2.  Рисование <xref:System.Windows.Forms.RadioButton> элементов управления в <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel> элемента управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.RadioButton>  
 [Общие сведения об элементе управления RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Общие сведения об элементе управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Элемент управления RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
