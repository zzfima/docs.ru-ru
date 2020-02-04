---
title: Группирование элементов управления с помощью элемента управления GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736648"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms
Windows Forms элементы управления <xref:System.Windows.Forms.GroupBox> используются для группирования других элементов управления. Существуют три причины группировки элементов управления.  
  
- Для создания визуального группирования связанных элементов формы для простого пользовательского интерфейса.  
  
- Для создания программного группирования (например, для переключателей).  
  
- Для перемещения элементов управления как единицы во время разработки.  
  
### <a name="to-create-a-group-of-controls"></a>Создание группы элементов управления  
  
1. Нарисуйте элемент управления <xref:System.Windows.Forms.GroupBox> в форме.  
  
2. Добавьте в поле группы другие элементы управления, нарисовав их внутри поля группы.  
  
     Если имеются существующие элементы управления, которые необходимо заключить в поле группы, можно выбрать все элементы управления, вырезать их в буфер обмена, выбрать элемент управления <xref:System.Windows.Forms.GroupBox> и вставить их в поле Группа. Их также можно перетащить в поле Группа.  
  
3. Задайте для свойства <xref:System.Windows.Forms.GroupBox.Text%2A> поля группы соответствующий заголовок.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.GroupBox>
- [Элемент управления GroupBox](groupbox-control-windows-forms.md)
