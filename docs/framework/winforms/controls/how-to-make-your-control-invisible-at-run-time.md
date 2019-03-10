---
title: Практическое руководство. Скрытие элемента управления во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: 52ea2336bac1ec483cb86e24114090a1b3725038
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708981"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Практическое руководство. Скрытие элемента управления во время выполнения
Бывают случаи, когда может потребоваться создать пользовательский элемент управления, который остается невидимым во время выполнения. Например элемент управления, который является будильника может быть невидимым, за исключением случаев, когда будильника. Это легко реализуется, задав <xref:System.Windows.Forms.Control.Visible%2A> свойство. Если <xref:System.Windows.Forms.Control.Visible%2A> свойство `true`, элемент управления отображается в обычном режиме. Если `false`, элемент управления будет скрыт. Несмотря на то, что код в элемент управления может выполняться будучи невидимым, вы не сможете взаимодействовать с элементом управления в пользовательском интерфейсе. Если вы хотите создать невидимому элементу управления, который реагирует на пользовательский ввод (например, щелчки мышью), следует создать прозрачный элемент управления. Дополнительные сведения см. в разделе [предоставления элемента управления прозрачный фон](how-to-give-your-control-a-transparent-background.md).  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>Чтобы скрыть элемент управления во время выполнения  
  
1.  Задайте для свойства <xref:System.Windows.Forms.Control.Visible%2A> значение `false`.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.Control.Visible%2A>
- [Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)
- [Практическое руководство. Установка степени прозрачности фона элемента управления](how-to-give-your-control-a-transparent-background.md)
