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
ms.openlocfilehash: dd7f238f8c20ba990158f23344e36376d3b1cb7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950538"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms
Элементы <xref:System.Windows.Forms.Label> управления Windows Forms могут использоваться для определения ключей доступа для других элементов управления. При определении ключа доступа в элементе управления Label пользователь может нажать клавишу ALT плюс символ, который вы указываете, чтобы переместить фокус на элемент управления, следующий за ним в последовательности табуляции. Поскольку метки не могут получать фокус, фокус автоматически перемещается к следующему элементу управления в последовательности табуляции. Используйте этот метод, чтобы назначить ключи доступа для текстовых полей, полей со списками, списков и сеток данных.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Назначение клавиши доступа элементу управления с меткой  
  
1. Сначала нарисуйте метку, а затем нарисуйте другой элемент управления.  
  
     -или-  
  
     Нарисуйте элементы управления в любом порядке и присвойте <xref:System.Windows.Forms.Control.TabIndex%2A> свойству метки значение на единицу меньше другого элемента управления.  
  
2. <xref:System.Windows.Forms.Label.UseMnemonic%2A> Присвойте`true`свойству метки значение.  
  
3. Используйте амперсанд (&) в <xref:System.Windows.Forms.Label.Text%2A> свойстве метки, чтобы назначить ключ доступа для метки. Дополнительные сведения см. в разделе [Создание ключей доступа для элементов управления Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    > Можно отобразить амперсанды в элементе управления Label, а не использовать их для создания ключей доступа. Это может произойти при привязке элемента управления Label к полю в наборе записей, где данные содержат амперсанды. Чтобы отобразить амперсанды в элементе управления Label, задайте <xref:System.Windows.Forms.Label.UseMnemonic%2A> для `false`свойства значение. Если вы хотите отображать амперсанды, а также ключ доступа, установите <xref:System.Windows.Forms.Label.UseMnemonic%2A> свойство в значение и укажите для `true` ключа доступа один амперсанд (&), а затем амперсанд для отображения с двумя амперсандами.  
  
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

- [Практическое руководство. Размер элемента управления метки Windows Forms в соответствии с его содержимым](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Общие сведения об элементе управления Label](label-control-overview-windows-forms.md)
- [Элемент управления Label](label-control-windows-forms.md)
