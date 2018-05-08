---
title: Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: fc9592981f3d926b2b5b85b6869da13dc644e7a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms
Windows Forms <xref:System.Windows.Forms.Label> элементы управления можно использовать для определения клавиши доступа для других элементов управления. При определении клавиши доступа в элементе управления label, пользователь может нажать клавишу ALT в сочетании с символом, передать фокус элементу управления, следующему в последовательности табуляции. Поскольку метки не может получать фокус, фокус автоматически перемещается к следующему элементу управления в последовательности табуляции. Этот метод используется для присвоения ключи доступа для текстовых полей, поля со списком, списки и таблицы данных.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Чтобы назначить клавиши доступа к элементу управления с меткой  
  
1.  Сначала нарисуйте метку, а затем другого элемента управления.  
  
     - или -  
  
     Нарисуйте элементы управления в любом порядке и задайте <xref:System.Windows.Forms.Control.TabIndex%2A> свойство метки на единицу меньше, чем у элемента управления.  
  
2.  Задайте для свойства label <xref:System.Windows.Forms.Label.UseMnemonic%2A> свойства `true`.  
  
3.  Используйте амперсанд (&) в метке <xref:System.Windows.Forms.Label.Text%2A> свойства, которому назначается ключ доступа для метки. Дополнительные сведения см. в разделе [Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Может потребоваться отобразить амперсанды в элементе управления label, а не использовать их для создания ключей доступа. Это может произойти, если элемент управления label привязан к полю в наборе записей, включающем амперсанды. Для отображения в элементе управления label амперсанды <xref:System.Windows.Forms.Label.UseMnemonic%2A> свойства `false`. Если вы хотите отобразить амперсанды и назначить клавишу доступа, установите <xref:System.Windows.Forms.Label.UseMnemonic%2A> свойства `true` и укажите клавишу доступа с помощью одного амперсанда (&) и знак для отображения с помощью двух знаков амперсанда.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [Общие сведения об элементе управления Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Элемент управления Label](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
