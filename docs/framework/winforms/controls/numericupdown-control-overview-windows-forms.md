---
title: Общие сведения об элементе управления NumericUpDown (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: b1f32a767d27ef2f4e5629947d67097272695d9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537165"
---
# <a name="numericupdown-control-overview-windows-forms"></a>Общие сведения об элементе управления NumericUpDown (Windows Forms)
<xref:System.Windows.Forms.NumericUpDown> Элемент управления выглядит как сочетание текстового поля и пары кнопок со стрелками для выбора значения пользователем. Он выводит и задает отдельное числовое значение в списке основных вариантов числовых значений. Пользователь может увеличить и уменьшить число вверх и Стрелка вниз, клавиши со стрелками вверх и вниз или введя число в части текстового поля элемента управления. Нажав клавишу со стрелкой вверх перемещает номер увеличивается до максимума; нажав клавишу со стрелкой вниз перемещение номера уменьшается до минимума.  
  
 Из-за универсальным функциональным возможностям этот элемент управления является очевидным выбором, например, если требуется создать музыкальный проигрыватель регулятор громкости. <xref:System.Windows.Forms.NumericUpDown> Управления используется во многих приложениях панели управления Windows.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Чисел, отображаемых в текстовом поле элемента управления могут находиться в различных форматах, включая шестнадцатеричное. Дополнительные сведения см. в разделе [как: Задание формата элемента управления NumericUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Ключевые свойства элемента управления являются <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (значение по умолчанию 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (значение по умолчанию 0), и <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (значение 1 по умолчанию). <xref:System.Windows.Forms.NumericUpDown.Value%2A> Свойство задает номер текущей выбраны в элементе управления. <xref:System.Windows.Forms.NumericUpDown.Increment%2A> Свойство задает значение, что номер настраивается, когда пользователь щелкает вверх или Стрелка вниз. При снятии фокуса управления любые введенные данные будет проверена на соответствие минимальным и максимальным числовые значения. Можно ускорить, элемент управления перемещается через чисел, когда пользователь нажимает постоянно вверх или Стрелка вниз, с <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> свойство. Основные методы элемента управления, <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> и <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.NumericUpDown>  
 [Элемент управления NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
