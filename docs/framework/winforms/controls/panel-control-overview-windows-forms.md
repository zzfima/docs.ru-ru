---
title: Общие сведения об элементе управления Panel
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744315"
---
# <a name="panel-control-overview-windows-forms"></a>Общие сведения об элементе управления Panel (Windows Forms)
Windows Forms элементы управления <xref:System.Windows.Forms.Panel> используются для предоставления идентифицируемого группирования для других элементов управления. Как правило, панели используются для разделения формы на функции. Например, у вас может быть форма заказа, в которой указываются параметры корреспонденции, такие как использование перевозчика в ночное время. Группирование всех параметров на панели дает пользователю логическую визуальную подсказку. Во время разработки все элементы управления можно легко перемещать — при перемещении элемента управления <xref:System.Windows.Forms.Panel> все содержащиеся в нем элементы управления также перемещаются. Доступ к элементам управления, сгруппированным в панели, можно получить с помощью свойства <xref:System.Windows.Forms.Control.Controls%2A>. Это свойство возвращает коллекцию экземпляров <xref:System.Windows.Forms.Control>, поэтому, как правило, необходимо привести элемент управления, полученный таким образом, к конкретному типу.  
  
## <a name="panel-versus-groupbox"></a>Панель и группа  
 Элемент управления <xref:System.Windows.Forms.Panel> аналогичен элементу управления <xref:System.Windows.Forms.GroupBox>; Тем не менее, только элемент управления <xref:System.Windows.Forms.Panel> может иметь полосы прокрутки, а только элемент управления <xref:System.Windows.Forms.GroupBox> отображает заголовок.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Чтобы отобразить полосы прокрутки, задайте для свойства <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> значение `true`. Внешний вид панели также можно настроить, задав свойства <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>и <xref:System.Windows.Forms.Panel.BorderStyle%2A>. Дополнительные сведения о свойствах <xref:System.Windows.Forms.Control.BackColor%2A> и <xref:System.Windows.Forms.Control.BackgroundImage%2A> см. в разделе [как задать фон панели](how-to-set-the-background-of-a-windows-forms-panel.md). Свойство <xref:System.Windows.Forms.Panel.BorderStyle%2A> определяет, отображается ли панель без видимой границы (<xref:System.Windows.Forms.BorderStyle.None>), простой линии (<xref:System.Windows.Forms.BorderStyle.FixedSingle>) или скрытой линии (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Panel>
- [Элемент управления GroupBox](groupbox-control-windows-forms.md)
- [Практическое руководство. Группирование элементов управления с элементом управления Panel в формах Windows Forms с помощью конструктора](group-controls-with-wf-panel-control-using-the-designer.md)
- [Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
