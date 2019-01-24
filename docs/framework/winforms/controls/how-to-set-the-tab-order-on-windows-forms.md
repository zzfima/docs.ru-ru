---
title: Как выполнить Установка последовательности переходов в формах Windows Forms
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
ms.openlocfilehash: 118785e14dddcd5ff19aa8c143f9e8df05d8980b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675263"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Как выполнить Установка последовательности переходов в формах Windows Forms
Последовательность табуляции заключается в порядке, в котором пользователь перемещает фокус от одного элемента управления в другую, нажав клавишу TAB. Каждая форма имеет свои собственные последовательности табуляции. По умолчанию последовательности табуляции совпадает в порядке создания элементов управления. Последовательности табуляции нумерация начинается с нуля.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-tab-order-of-a-control"></a>Чтобы задать последовательность перехода элемента управления  
  
1.  На **представление** меню, щелкните **последовательности табуляции**.  
  
     Это активирует режим выбора последовательности табуляции в форме. Число (представляющий <xref:System.Windows.Forms.Control.TabIndex%2A> свойство) отображается в левом верхнем углу каждого элемента управления.  
  
2.  Щелкните элементы управления последовательно, чтобы установить нужные последовательности табуляции.  
  
    > [!NOTE]
    >  Место элемента управления в последовательности табуляции можно присвоить любое значение больше или равно 0. Для дубликатов оценивается z порядка двух элементов управления и элемент управления в верхней части является первой вкладкой. (Z порядок является видимое расположение элементов управления на форме вдоль оси z формы [глубины]. Z порядок определяет, какие элементы управления располагаются перед другими элементами.) Дополнительные сведения о z порядка, см. в разделе [иерархическое представление объектов в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
3.  Когда вы закончите, нажмите кнопку **последовательности табуляции** на **представление** меню еще раз, чтобы выйти из режима выбора последовательности перехода.  
  
    > [!NOTE]
    >  Элементы управления, которые не удается получить фокус, а также отключенные и невидимые элементы управления, не имеют <xref:System.Windows.Forms.Control.TabIndex%2A> свойство и не включаются в последовательности табуляции. Как пользователь нажимает клавишу TAB, эти элементы управления, пропускаются.  
  
 Кроме того, можно задать последовательность перехода в окно свойств с помощью <xref:System.Windows.Forms.Control.TabIndex%2A> свойство. <xref:System.Windows.Forms.Control.TabIndex%2A> Свойства элемента управления определяет позицию в последовательности табуляции. По умолчанию отображается первый элемент управления имеет <xref:System.Windows.Forms.Control.TabIndex%2A> значение 0, второй — <xref:System.Windows.Forms.Control.TabIndex%2A> 1 и т. д.  
  
 Кроме того, по умолчанию <xref:System.Windows.Forms.GroupBox> управления имеет свой собственный <xref:System.Windows.Forms.Control.TabIndex%2A> значение, являющееся целым числом. Объект <xref:System.Windows.Forms.GroupBox> сам элемент управления не может иметь фокус во время выполнения. Таким образом, каждый элемент управления внутри <xref:System.Windows.Forms.GroupBox> имеет свое десятичное <xref:System.Windows.Forms.Control.TabIndex%2A> значение, начинающееся с.0. Естественно, как <xref:System.Windows.Forms.Control.TabIndex%2A> из <xref:System.Windows.Forms.GroupBox> управления, элементы управления внутри него будут увеличиваться соответственно. Если вы изменили <xref:System.Windows.Forms.Control.TabIndex%2A> значение от 5 до 6, <xref:System.Windows.Forms.Control.TabIndex%2A> значение первого элемента в группе автоматически изменяется на 6.0 и т. д.  
  
 Наконец любой элемент управления из многочисленных в форме может быть пропущено в последовательности табуляции. Как правило нажав клавишу TAB последовательно во время выполнения выделяется каждый элемент управления в последовательности табуляции. Отключив <xref:System.Windows.Forms.Control.TabStop%2A> свойство, можно сделать элемент управления включался в последовательности табуляции элементов формы.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>Чтобы удалить элемент управления из последовательности табуляции  
  
1.  Задайте в качестве <xref:System.Windows.Forms.Control.TabStop%2A> свойства `false` в окне «Свойства».  
  
     Объект со свойством <xref:System.Windows.Forms.Control.TabStop%2A> было присвоено свойство `false` сохраняет свое место в последовательности табуляции, несмотря на то, что этот элемент управления пропускается, если цикл по элементам управления с помощью клавиши TAB.  
  
    > [!NOTE]
    >  Группы переключателей есть одна позиция табуляции во время выполнения. Выбранную кнопку (то есть кнопка с его <xref:System.Windows.Forms.RadioButton.Checked%2A> свойству присвоено `true`) имеет его <xref:System.Windows.Forms.Control.TabStop%2A> свойству автоматически присваивается `true`, тогда как другие кнопки имеют свои <xref:System.Windows.Forms.Control.TabStop%2A> свойству присвоено `false`. Дополнительные сведения о группировании <xref:System.Windows.Forms.RadioButton> элементов управления, см. в разделе [группирования Windows Forms элементов управления RadioButton как набор](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## <a name="see-also"></a>См. также
- [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)
- [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
