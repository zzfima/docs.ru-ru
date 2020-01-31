---
title: Задать порядок табуляции элементов управления
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5d53e411bda0279271e4f73e1842c52fd6d9b3a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746828"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Как задать порядок табуляции на Windows Forms

Порядок табуляции — это порядок, в котором пользователь перемещает фокус с одного элемента управления на другой, нажимая клавишу TAB. Каждая форма имеет собственный порядок табуляции. По умолчанию порядок табуляции совпадает с порядком, в котором были созданы элементы управления. Нумерация в порядке табуляции начинается с нуля.

## <a name="to-set-the-tab-order-of-a-control"></a>Установка последовательности табуляции элемента управления

1. В Visual Studio в меню **вид** выберите **последовательность табуляции**.

   Это активирует режим выбора порядка табуляции в форме. Число (представляющее свойство <xref:System.Windows.Forms.Control.TabIndex%2A>) отображается в левом верхнем углу каждого элемента управления.

2. Последовательно щелкните элементы управления, чтобы установить нужный порядок табуляции.

   > [!NOTE]
   > В качестве места элемента управления в последовательности табуляции можно задать любое значение, большее или равное 0. При возникновении дубликатов вычисляется z-порядок двух элементов управления, а сначала элемент управления на вкладке сверху. (Z-порядок — это визуальное расположение элементов управления в форме вдоль оси z формы [depth]. Z-порядок определяет, какие элементы управления находятся перед другими элементами управления.) Дополнительные сведения о z-порядке см. [в разделе слоевые объекты на Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. По завершении выберите в меню **вид** пункт **последовательность табуляции** , чтобы выйти из режима последовательности табуляции.

   > [!NOTE]
   > Элементы управления, которые не могут получить фокус, а также отключенные и невидимые элементы управления, не имеют свойства <xref:System.Windows.Forms.Control.TabIndex%2A> и не включаются в последовательность табуляции. Когда пользователь нажимает клавишу TAB, эти элементы управления пропускаются.

Кроме того, можно задать порядок табуляции в окно свойств с помощью свойства <xref:System.Windows.Forms.Control.TabIndex%2A>. Свойство <xref:System.Windows.Forms.Control.TabIndex%2A> элемента управления определяет, где оно находится в последовательности табуляции. По умолчанию Первый рисуемый элемент управления имеет <xref:System.Windows.Forms.Control.TabIndex%2A> значение 0, второй имеет <xref:System.Windows.Forms.Control.TabIndex%2A> 1 и т. д.

Кроме того, по умолчанию элемент управления <xref:System.Windows.Forms.GroupBox> имеет собственное значение <xref:System.Windows.Forms.Control.TabIndex%2A>, которое является целым числом. Сам элемент управления <xref:System.Windows.Forms.GroupBox> не может иметь фокус во время выполнения. Таким же, каждый элемент управления в <xref:System.Windows.Forms.GroupBox> имеет собственное десятичное <xref:System.Windows.Forms.Control.TabIndex%2A> значение, начинающееся с. 0. Естественно, по мере увеличения <xref:System.Windows.Forms.Control.TabIndex%2A> элемента управления <xref:System.Windows.Forms.GroupBox> элементы управления внутри него будут соответственно увеличены. Если вы изменили значение <xref:System.Windows.Forms.Control.TabIndex%2A> с 5 на 6, <xref:System.Windows.Forms.Control.TabIndex%2A> значение первого элемента управления в группе автоматически изменится на 6,0 и т. д.

Наконец, любой элемент управления множества в форме можно пропустить в последовательности табуляции. Как правило, при последовательном нажатии клавиши Tab во время выполнения выбирается каждый элемент управления в последовательности табуляции. Отключив свойство <xref:System.Windows.Forms.Control.TabStop%2A>, можно сделать элемент управления передаваться в порядке табуляции в форме.

## <a name="to-remove-a-control-from-the-tab-order"></a>Удаление элемента управления из последовательности табуляции

Присвойте свойству <xref:System.Windows.Forms.Control.TabStop%2A> элемента управления **значение false** в окне **свойства** .

Элемент управления, свойство <xref:System.Windows.Forms.Control.TabStop%2A> которого имеет значение `false` по-прежнему сохраняет свое расположение в последовательности табуляции, даже если элемент управления пропускается при цикле по элементам управления с помощью клавиши TAB.

> [!NOTE]
> Группа переключателей содержит одну позицию табуляции во время выполнения. Для выбранной кнопки (т. е. для кнопки со свойством <xref:System.Windows.Forms.RadioButton.Checked%2A>, установленным в `true`) свойство <xref:System.Windows.Forms.Control.TabStop%2A> автоматически устанавливается в `true`, а для других кнопок свойство <xref:System.Windows.Forms.Control.TabStop%2A> имеет значение `false`. Дополнительные сведения о группировании элементов управления <xref:System.Windows.Forms.RadioButton> см. [в разделе группирование Windows Forms элементов управления RadioButton для работы в виде набора](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>См. также:

- [Элементы управления Windows Forms](index.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
