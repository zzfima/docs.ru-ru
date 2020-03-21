---
title: Практическое руководство. Отображение цветовой палитры с помощью компонента ColorDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141787"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Практическое руководство. Отображение цветовой палитры с помощью компонента ColorDialog
Компонент [ColorDialog](colordialog-component-windows-forms.md) отображает палитру цветов и возвращает свойство, содержащее выбранный пользователем цвет.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Выбрать цвет с помощью компонента ColorDialog  
  
1. Отображение диалогового окна с помощью метода. <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>  
  
2. Используйте <xref:System.Windows.Forms.DialogResult> свойство, чтобы определить, как был закрыт диалоговый ящик.  
  
3. Используйте <xref:System.Windows.Forms.ColorDialog.Color%2A> свойство <xref:System.Windows.Forms.ColorDialog> компонента для установки выбранного цвета.  
  
     В приведенном ниже <xref:System.Windows.Forms.Button> примере <xref:System.Windows.Forms.Control.Click> обработчик <xref:System.Windows.Forms.ColorDialog> событий элемента управления открывает компонент. Когда цвет выбран и пользователь нажимает **OK,** цвет фона <xref:System.Windows.Forms.Button> управления устанавливается на выбранный цвет. Пример предполагает, что ваша <xref:System.Windows.Forms.Button> форма <xref:System.Windows.Forms.ColorDialog> имеет элемент управления и компонент.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     (Визуальный СЗ, Визуальный СЗ) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ColorDialog>
- [Компонент ColorDialog](colordialog-component-windows-forms.md)
