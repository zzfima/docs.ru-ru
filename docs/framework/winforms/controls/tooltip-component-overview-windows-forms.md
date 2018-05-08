---
title: Общие сведения о компоненте ToolTip (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: e31bb1169eeedd85a92e3bf96318623696020f9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tooltip-component-overview-windows-forms"></a>Общие сведения о компоненте ToolTip (Windows Forms)
Компонент <xref:System.Windows.Forms.ToolTip> в Windows Forms отображает текст при наведении указателя мыши на элементы управления. Компонент ToolTip можно связать с любым элементом управления. Пример использования этого компонента: для экономии места в форме маленького значка для кнопки и использовать компонент ToolTip для объяснения ее функции.  
  
## <a name="working-with-the-tooltip-component"></a>Работа с компонентом ToolTip  
 Объект <xref:System.Windows.Forms.ToolTip> компонент предоставляет `ToolTip` свойства для нескольких элементов управления на форму Windows или другой контейнер. Например, если одна <xref:System.Windows.Forms.ToolTip> компонент на форме, можно отобразить «Введите здесь имя» для <xref:System.Windows.Forms.TextBox> управления и щелкните здесь, чтобы сохранить изменения» для <xref:System.Windows.Forms.Button> элемента управления.  
  
 Основные методы <xref:System.Windows.Forms.ToolTip> , компонент <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> и <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. Можно использовать <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод, чтобы задать подсказки, отображаемый для элементов управления. Дополнительные сведения см. в разделе [как: задайте подсказки для элементов управления формы Windows Forms во время разработки](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Ключевые свойства, <xref:System.Windows.Forms.ToolTip.Active%2A>, которое должно быть равно `true` для подсказки, которая отображается, и <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, который задает время, строки всплывающей подсказки, как долго пользователь должен указывать на элемент управления для подсказки, которая отображается и как его длину принимает окна очередной всплывающей подсказки для отображения. Дополнительные сведения см. в разделе [как: изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolTip>  
 [Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
