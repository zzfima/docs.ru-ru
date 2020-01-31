---
title: Общие сведения об элементе управления RadioButton
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: bbc93046b69d39caadde4986ff56f067fc206a9e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741137"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Общие сведения об элементе управления RadioButton (Windows Forms)
Windows Forms элементы управления <xref:System.Windows.Forms.RadioButton> представляют собой набор из двух или более взаимоисключающих вариантов выбора для пользователя. Хотя переключатели и флажки могут работать аналогично, существует важное отличие: когда пользователь выбирает переключатель, другие переключатели в той же группе также не могут быть выбраны. Напротив, можно выбрать любое количество флажков. Определение группы переключателей говорит пользователю: "ниже приведен набор вариантов, из которых можно выбрать один и только один."  
  
## <a name="using-the-control"></a>Использование элемента управления  
 При щелчке элемента управления <xref:System.Windows.Forms.RadioButton> его свойство <xref:System.Windows.Forms.RadioButton.Checked%2A> имеет значение `true` и вызывается обработчик событий <xref:System.Windows.Forms.Control.Click>. Событие <xref:System.Windows.Forms.RadioButton.CheckedChanged> возникает при изменении значения свойства <xref:System.Windows.Forms.RadioButton.Checked%2A>. Если свойство <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> имеет значение `true` (по умолчанию), то при выборе переключателя все остальные в группе автоматически очищаются. Это свойство обычно устанавливается в `false` только при использовании кода проверки, чтобы убедиться, что переключатель выбран как допустимый параметр. Текст, отображаемый в элементе управления, задается свойством <xref:System.Windows.Forms.Control.Text%2A>, которое может содержать сочетания клавиш для доступа. Ключ доступа позволяет пользователю "щелкнуть" элемент управления, нажав клавишу ALT с клавишей доступа. Дополнительные сведения см. [в разделах как создать ключи доступа для Windows Formsных элементов управления](how-to-create-access-keys-for-windows-forms-controls.md) и [как задать текст, отображаемый элементом управления Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Элемент управления <xref:System.Windows.Forms.RadioButton> может выглядеть как кнопка команды, которая, по-видимому, была нажата, если выбрано свойство <xref:System.Windows.Forms.RadioButton.Appearance%2A> значение <xref:System.Windows.Forms.Appearance.Button>. Переключатели также могут отображать изображения с помощью свойств <xref:System.Windows.Forms.ButtonBase.Image%2A> и <xref:System.Windows.Forms.ButtonBase.ImageList%2A>. Дополнительные сведения см. в разделе [как задать изображение, отображаемое элементом управления Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.RadioButton>
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
- [Общие сведения об элементе управления GroupBox](groupbox-control-overview-windows-forms.md)
- [Общие сведения об элементе управления CheckBox](checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)
- [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [Элемент управления RadioButton](radiobutton-control-windows-forms.md)
