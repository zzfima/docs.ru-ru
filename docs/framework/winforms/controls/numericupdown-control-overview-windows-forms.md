---
title: Общие сведения об элементе управления NumericUpDown
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 3e24fa543df9028e9866d91ec60c3cf88578ac56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740801"
---
# <a name="numericupdown-control-overview-windows-forms"></a>Общие сведения об элементе управления NumericUpDown (Windows Forms)
Элемент управления <xref:System.Windows.Forms.NumericUpDown> выглядит как сочетание текстового поля и пары стрелок, которые пользователь может щелкнуть для корректировки значения. Элемент управления отображает и задает отдельное числовое значение из списка вариантов фиксированного числового значения. Пользователь может увеличивать и уменьшать число, щелкая стрелки вверх и вниз, нажимая клавиши со СТРЕЛКАми вверх и вниз или вводя число в текстовое поле элемента управления. При нажатии клавиши со стрелкой вверх число перемещается в сторону максимума; При нажатии клавиши со стрелкой вниз число перемещается в сторону минимума.  
  
 Из-за универсальной функциональности этот элемент управления является очевидным выбором, например, если требуется создать регулятор громкости для приложения музыкального проигрывателя. Элемент управления <xref:System.Windows.Forms.NumericUpDown> используется во многих приложениях панели управления Windows.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Числа, отображаемые в текстовом поле элемента управления, могут быть в различных форматах, включая шестнадцатеричные. Дополнительные сведения см. в разделе [инструкции. Задание формата для элемента управления Windows Forms NumericUpDown](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Ключевыми свойствами элемента управления являются <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (значение по умолчанию 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (значение по умолчанию — 0) и <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (значение по умолчанию 1). Свойство <xref:System.Windows.Forms.NumericUpDown.Value%2A> задает текущее число, выбранное в элементе управления. Свойство <xref:System.Windows.Forms.NumericUpDown.Increment%2A> задает величину, на которую корректируется число, когда пользователь щелкает стрелку вверх или вниз. Когда фокус перемещается с элемента управления, любые типизированные входные данные будут проверяться на соответствие минимальному и максимальному числовому значению. Можно увеличить скорость перемещения элемента управления по числам, когда пользователь постоянно нажимает кнопку со стрелкой вверх или вниз со свойством <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>. Ключевыми методами элемента управления являются <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> и <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.NumericUpDown>
- [Элемент управления NumericUpDown](numericupdown-control-windows-forms.md)
- [Практическое руководство. Определение формата элемента управления NumericUpDown в Windows Forms](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
