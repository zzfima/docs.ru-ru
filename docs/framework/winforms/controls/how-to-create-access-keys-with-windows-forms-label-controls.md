---
title: Создание ключей доступа с помощью элементов управления Label
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
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731048"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms
Windows Forms элементы управления <xref:System.Windows.Forms.Label> можно использовать для определения ключей доступа для других элементов управления. При определении ключа доступа в элементе управления Label пользователь может нажать клавишу ALT плюс символ, который вы указываете, чтобы переместить фокус на элемент управления, следующий за ним в последовательности табуляции. Поскольку метки не могут получать фокус, фокус автоматически перемещается к следующему элементу управления в последовательности табуляции. Используйте этот метод, чтобы назначить ключи доступа для текстовых полей, полей со списками, списков и сеток данных.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Назначение клавиши доступа элементу управления с меткой  
  
1. Сначала нарисуйте метку, а затем нарисуйте другой элемент управления.  
  
     -или-  
  
     Нарисуйте элементы управления в любом порядке и присвойте свойству <xref:System.Windows.Forms.Control.TabIndex%2A> метки значение на единицу меньше, чем у другого элемента управления.  
  
2. Задайте для свойства <xref:System.Windows.Forms.Label.UseMnemonic%2A> метки значение `true`.  
  
3. Используйте амперсанд (&) в свойстве <xref:System.Windows.Forms.Label.Text%2A> метки, чтобы назначить ключ доступа для метки. Дополнительные сведения см. в разделе [Создание ключей доступа для элементов управления Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    > Можно отобразить амперсанды в элементе управления Label, а не использовать их для создания ключей доступа. Это может произойти при привязке элемента управления Label к полю в наборе записей, где данные содержат амперсанды. Чтобы отобразить амперсанды в элементе управления Label, задайте для свойства <xref:System.Windows.Forms.Label.UseMnemonic%2A> значение `false`. Если вы хотите отображать амперсанды, а также ключ доступа, задайте для свойства <xref:System.Windows.Forms.Label.UseMnemonic%2A> значение `true` и укажите в качестве клавиши доступа один амперсанд (&) и амперсанд для отображения с двумя амперсандами.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Общие сведения об элементе управления Label](label-control-overview-windows-forms.md)
- [Элемент управления Label](label-control-windows-forms.md)
