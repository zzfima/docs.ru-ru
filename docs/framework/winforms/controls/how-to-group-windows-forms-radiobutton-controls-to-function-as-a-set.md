---
title: Группирование элементов управления RadioButton для работы в качестве набора
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732949"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms
Windows Forms элементы управления <xref:System.Windows.Forms.RadioButton> предназначены для того, чтобы предоставить пользователям выбор между двумя или более параметрами, из которых только один может быть назначен процедуре или объекту. Например, группа элементов управления <xref:System.Windows.Forms.RadioButton> может отображать один или несколько перевозчиков пакетов для заказа, но будут использоваться только те из них. Поэтому можно выбрать только один <xref:System.Windows.Forms.RadioButton> за раз, даже если он является частью функциональной группы.  
  
 Переключатели группируются путем их рисования внутри контейнера, например элемента управления <xref:System.Windows.Forms.Panel>, элемента управления <xref:System.Windows.Forms.GroupBox> или формы. Все переключатели, добавленные непосредственно в форму, становятся одной группой. Чтобы добавить отдельные группы, необходимо поместить их внутри панелей или групп. Дополнительные сведения о панелях или полях групп см. в разделе Общие сведения об [элементе управления Panel](panel-control-overview-windows-forms.md) или [элементе управления GroupBox](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Группировка элементов управления RadioButton как набора, который будет функционировать независимо от других наборов  
  
1. Перетащите <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel> элемент управления с вкладки **Windows Forms** на **панели элементов** в форму.  
  
2. Рисование <xref:System.Windows.Forms.RadioButton> элементов управления в <xref:System.Windows.Forms.GroupBox> или элементе управления <xref:System.Windows.Forms.Panel>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RadioButton>
- [Общие сведения об элементе управления RadioButton](radiobutton-control-overview-windows-forms.md)
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
- [Общие сведения об элементе управления GroupBox](groupbox-control-overview-windows-forms.md)
- [Общие сведения об элементе управления CheckBox](checkbox-control-overview-windows-forms.md)
- [Элемент управления RadioButton](radiobutton-control-windows-forms.md)
