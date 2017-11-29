---
title: "Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 37d8571624272f62c6ce327b0ed25e082c5cf713
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
