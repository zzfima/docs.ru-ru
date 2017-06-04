---
title: "Практическое руководство. Определение значка для кнопки элемента управления ToolBar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "кнопки [Windows Forms], значки"
  - "примеры [Windows Forms], панели инструментов"
  - "значки [Windows Forms], кнопки панели инструментов"
  - "изображения [Windows Forms], кнопки панели инструментов"
  - "ToolBar - элемент управления [Windows Forms], добавление значков на кнопки"
  - "панели инструментов [Windows Forms], добавление значков на кнопки"
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Определение значка для кнопки элемента управления ToolBar
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Для удобства распознавания пользователями кнопки <xref:System.Windows.Forms.ToolBar> способны отображать значки.  Это можно сделать, добавив изображения в компонент [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и затем связав компонент <xref:System.Windows.Forms.ImageList> с элементом управления <xref:System.Windows.Forms.ToolBar>.  
  
### Задание значка для кнопки панели инструментов программными средствами  
  
1.  В процедуре создайте экземпляр компонента <xref:System.Windows.Forms.ImageList> и элемента управления <xref:System.Windows.Forms.ToolBar>.  
  
2.  В той же процедуре задайте изображение для компонента <xref:System.Windows.Forms.ImageList>.  
  
3.  В той же процедуре свяжите элемент управления <xref:System.Windows.Forms.ImageList> с элементом управления <xref:System.Windows.Forms.ToolBar> и определите свойство <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> отдельных кнопок панели инструментов.  
  
     В следующем примере кода в качестве местоположения изображения выбрана папка **Мои документы**.  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  В примере, представленном ниже, подразумевается, что элемент управления <xref:System.Windows.Forms.PictureBox> уже добавлен в форму.  
  
     Если следовать приведенным выше инструкциям, получится код, аналогичный следующему.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.ToolBar>   
 [Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Элемент управления ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)