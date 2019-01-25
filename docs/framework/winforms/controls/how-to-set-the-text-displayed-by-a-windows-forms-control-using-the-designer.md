---
title: Как выполнить Задать текст, отображаемый элементом управления, с помощью конструктора форм Windows
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: cea2bcdb973e1deb5e0e6cf7fcc31b7c084dc446
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510589"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>Как выполнить Задать текст, отображаемый элементом управления, с помощью конструктора форм Windows
Элементы управления Windows Forms обычно отображается текст, связанный с их основной функцией элемента управления. Например <xref:System.Windows.Forms.Button> управления обычно отображается заголовок, указывающее, какое действие выполняется при нажатии кнопки. С помощью свойства <xref:System.Windows.Forms.Control.Text%2A> можно задавать или получать текст для всех элементов управления. Шрифт можно менять с помощью свойства <xref:System.Windows.Forms.Control.Font%2A>.  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a>Для задания текста и шрифта с помощью конструктора  
  
1.  В окне «Свойства» задайте <xref:System.Windows.Forms.Control.Text%2A> свойство элемента управления соответствующую строку.  
  
     Чтобы создать сочетание клавиш, поставьте амперсанд (&) перед буквой, которая будет использоваться сочетание клавиш.  
  
2.  В окне «Свойства» нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.Control.Font%2A> свойство.  
  
     В диалоговом окне стандартного шрифта выберите шрифт, стиль шрифта, размер, эффекты (например, зачеркивание или подчеркивание) и сценарий, которые должны.  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Задать текст, отображаемый элементом управления форм Windows](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
