---
title: Практическое руководство. Определение значка для кнопки элемента управления ToolBar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: 84c67c7d2584390ba3e48cb83820c65c6bb45d1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182213"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a>Практическое руководство. Определение значка для кнопки элемента управления ToolBar
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 <xref:System.Windows.Forms.ToolBar>кнопки могут отображать значки внутри них для легкой идентификации пользователями. Это достигается путем добавления [изображений в компонент Компонент ImageList,](imagelist-component-windows-forms.md) а затем связывания <xref:System.Windows.Forms.ImageList> компонента с элементом <xref:System.Windows.Forms.ToolBar> управления.  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a>Установить значок для кнопки панели инструментов программно  
  
1. В процедуре мгновенно ели <xref:System.Windows.Forms.ImageList> компонент <xref:System.Windows.Forms.ToolBar> и элемент управления.  
  
2. В той же процедуре присвоите изображение компоненту. <xref:System.Windows.Forms.ImageList>  
  
3. В той же процедуре, назначить <xref:System.Windows.Forms.ImageList> элемент управления для <xref:System.Windows.Forms.ToolBar> управления и назначить свойство <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> отдельных кнопок панели инструментов.  
  
     В следующем примере кода путь, установленный для расположения изображения, является папкой **«Мои документы».** Это делается, потому что можно предположить, что большинство компьютеров под управлением операционной системы Windows будет включать в себя этот каталог. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение. Приведенный ниже пример предполагает <xref:System.Windows.Forms.PictureBox> форму с уже добавленным элементом управления.  
  
     Следуя вышеприведенным шагам, вы должны были написать код, аналогичный тому, который отображается ниже.  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolBar>
- [Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Элемент управления ToolBar](toolbar-control-windows-forms.md)
- [Компонент ImageList](imagelist-component-windows-forms.md)
