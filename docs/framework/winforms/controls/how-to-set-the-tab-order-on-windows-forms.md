---
title: "Практическое руководство. Установка последовательности переходов в формах Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d514b20381b44102076c776d12181df3838e4eaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Практическое руководство. Установка последовательности переходов в формах Windows Forms
Последовательность табуляции — это порядок, в которой пользователь передвигает фокус с одного элемента управления на другой с помощью клавиши TAB. Каждая форма имеет свои собственные последовательности табуляции. По умолчанию последовательности табуляции является таким же, как порядок создания элементов управления. Последовательность перехода нумерация начинается с нуля.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-the-tab-order-of-a-control"></a>Чтобы задать последовательность перехода элемента управления  
  
1.  На **представление** меню, нажмите кнопку **последовательности табуляции**.  
  
     Это активирует режим выбора последовательности переходов в форме. Число (представляющий <xref:System.Windows.Forms.Control.TabIndex%2A> свойство) отображается в левом верхнем углу каждого элемента управления.  
  
2.  Щелкните последовательно, чтобы установить нужные последовательности табуляции элементов управления.  
  
    > [!NOTE]
    >  Поместить элемент управления в последовательности перехода может быть присвоено любое значение больше или равно 0. Для дубликатов оценивается z порядка двух элементов управления и элемент управления в верхней части является первой вкладкой. (Z порядка является видимое расположение элементов управления на форме вдоль оси z формы [глубины]. Z порядок определяет, какие элементы управления располагаются перед другими элементами.) Дополнительные сведения о z порядке см. в разделе [иерархическое представление объектов в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
3.  После завершения нажмите кнопку **последовательности табуляции** на **представление** меню еще раз, чтобы выйти из режима выбора последовательности перехода.  
  
    > [!NOTE]
    >  Элементы управления, которые не удается получить фокус, а также отключенные и невидимые элементы управления, не имеют <xref:System.Windows.Forms.Control.TabIndex%2A> свойство и не включаются в последовательности табуляции. При нажатии клавиши TAB, эти элементы управления пропускаются.  
  
 Кроме того, можно задать последовательность перехода в окно свойств с помощью <xref:System.Windows.Forms.Control.TabIndex%2A> свойство. <xref:System.Windows.Forms.Control.TabIndex%2A> Свойство элемента управления определяет, где он расположен в последовательности табуляции. По умолчанию используется первый элемент управления рисуется <xref:System.Windows.Forms.Control.TabIndex%2A> значение 0, второй — <xref:System.Windows.Forms.Control.TabIndex%2A> 1 и т. д.  
  
 Кроме того, по умолчанию <xref:System.Windows.Forms.GroupBox> управления имеет свой собственный <xref:System.Windows.Forms.Control.TabIndex%2A> значение, которое является целым числом. Объект <xref:System.Windows.Forms.GroupBox> сам элемент управления не может иметь фокус во время выполнения. Таким образом, каждый элемент управления внутри <xref:System.Windows.Forms.GroupBox> имеет свое десятичное <xref:System.Windows.Forms.Control.TabIndex%2A> значение, начинающееся с.0. Естественно, как <xref:System.Windows.Forms.Control.TabIndex%2A> из <xref:System.Windows.Forms.GroupBox> управления увеличивается, элементы управления внутри него будут увеличиваться соответственно. Если вы изменили <xref:System.Windows.Forms.Control.TabIndex%2A> значение от 5 до 6, <xref:System.Windows.Forms.Control.TabIndex%2A> значение первого элемента в группе автоматически изменяется 6.0 и т. д.  
  
 Наконец любой элемент управления из множества элементов формы может быть пропущен в последовательности табуляции. Как правило при нажатии клавиши TAB последовательно во время выполнения выделяется каждый элемент управления в последовательности табуляции. Отключив <xref:System.Windows.Forms.Control.TabStop%2A> можно сделать элемент управления передается в последовательности перехода формы.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>Чтобы удалить элемент управления в последовательности табуляции  
  
1.  Задайте в качестве <xref:System.Windows.Forms.Control.TabStop%2A> свойства `false` в окне «Свойства».  
  
     Элемент управления типа <xref:System.Windows.Forms.Control.TabStop%2A> присвоено свойству `false` сохраняет свое место в последовательности перехода, несмотря на то, что этот элемент управления пропускается при переходе по элементам управления с помощью клавиши TAB.  
  
    > [!NOTE]
    >  В переключателе есть одна позиция табуляции во время выполнения. Выделенной кнопки (то есть кнопка с его <xref:System.Windows.Forms.RadioButton.Checked%2A> свойство `true`) имеет его <xref:System.Windows.Forms.Control.TabStop%2A> свойству автоматически присваивается `true`, тогда как другие кнопки их <xref:System.Windows.Forms.Control.TabStop%2A> свойство `false`. Дополнительные сведения о группировании <xref:System.Windows.Forms.RadioButton> элементов управления, в разделе [группирование Windows Forms элементов управления RadioButton как набор](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
