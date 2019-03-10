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
ms.openlocfilehash: 35f6f81c2b13234b23b3b2295e45caf5f16abd9e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708331"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="43b45-102">Практическое руководство. Отображение цветовой палитры с помощью компонента ColorDialog</span><span class="sxs-lookup"><span data-stu-id="43b45-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="43b45-103">[ColorDialog](colordialog-component-windows-forms.md) компонент отображает палитру цветов и возвращает свойство, содержащее цвет, выбранном пользователем.</span><span class="sxs-lookup"><span data-stu-id="43b45-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="43b45-104">Чтобы выбрать цвет с помощью компонента ColorDialog</span><span class="sxs-lookup"><span data-stu-id="43b45-104">To choose a color using the ColorDialog component</span></span>  
  
1.  <span data-ttu-id="43b45-105">Отобразить диалоговое окно с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="43b45-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="43b45-106">Используйте <xref:System.Windows.Forms.DialogResult> свойства, чтобы определить, как окно было закрыто.</span><span class="sxs-lookup"><span data-stu-id="43b45-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="43b45-107">Используйте <xref:System.Windows.Forms.ColorDialog.Color%2A> свойство <xref:System.Windows.Forms.ColorDialog> компонента для присвоения выбранный цвет.</span><span class="sxs-lookup"><span data-stu-id="43b45-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="43b45-108">В следующем примере <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий открывает <xref:System.Windows.Forms.ColorDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="43b45-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="43b45-109">Если цвет — выбран и пользователь нажимает **ОК**, <xref:System.Windows.Forms.Button> цвет фона элемента управления имеет значение на выбранный цвет.</span><span class="sxs-lookup"><span data-stu-id="43b45-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="43b45-110">В примере предполагается, в форме есть <xref:System.Windows.Forms.Button> управления и <xref:System.Windows.Forms.ColorDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="43b45-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="43b45-111">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="43b45-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="43b45-112">См. также</span><span class="sxs-lookup"><span data-stu-id="43b45-112">See also</span></span>
- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="43b45-113">Компонент ColorDialog</span><span class="sxs-lookup"><span data-stu-id="43b45-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
