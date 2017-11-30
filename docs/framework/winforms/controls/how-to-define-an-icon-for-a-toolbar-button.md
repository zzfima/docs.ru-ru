---
title: "Практическое руководство. Определение значка для кнопки элемента управления ToolBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d9f1dc73e6a74d8d69fedf6650102b77bd4f96a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="c73be-102">Практическое руководство. Определение значка для кнопки элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="c73be-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
>  <span data-ttu-id="c73be-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="c73be-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="c73be-104"><xref:System.Windows.Forms.ToolBar>кнопки, могут отображать значки для упрощения идентификации пользователей.</span><span class="sxs-lookup"><span data-stu-id="c73be-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="c73be-105">Это можно сделать, добавив изображения [компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) компонента, а затем связать <xref:System.Windows.Forms.ImageList> компонент с <xref:System.Windows.Forms.ToolBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c73be-105">This is achieved through adding images to the [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="c73be-106">Чтобы задать значок для кнопки панели инструментов программным способом</span><span class="sxs-lookup"><span data-stu-id="c73be-106">To set an icon for a toolbar button programmatically</span></span>  
  
1.  <span data-ttu-id="c73be-107">В процедуре создания экземпляра <xref:System.Windows.Forms.ImageList> компонента и <xref:System.Windows.Forms.ToolBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c73be-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2.  <span data-ttu-id="c73be-108">В той же процедуре задайте изображение для <xref:System.Windows.Forms.ImageList> компонента.</span><span class="sxs-lookup"><span data-stu-id="c73be-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3.  <span data-ttu-id="c73be-109">В той же процедуры, назначить <xref:System.Windows.Forms.ImageList> управления <xref:System.Windows.Forms.ToolBar> управления и назначить <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> свойства отдельных кнопок панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="c73be-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="c73be-110">В следующем примере кода путь задан при размещении изображения является **Мои документы** папки.</span><span class="sxs-lookup"><span data-stu-id="c73be-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="c73be-111">Эта операция необходима, поскольку можно предположить, что большинство компьютеров под управлением операционной системы Windows включает этот каталог.</span><span class="sxs-lookup"><span data-stu-id="c73be-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="c73be-112">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="c73be-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="c73be-113">В приведенном ниже примере предполагается наличие формы с <xref:System.Windows.Forms.PictureBox> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="c73be-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="c73be-114">Следующие действия, перечисленные выше должен быть сохранен код, аналогичный, показаны ниже.</span><span class="sxs-lookup"><span data-stu-id="c73be-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c73be-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c73be-115">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="c73be-116">Практическое руководство. Активация событий меню для кнопок элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="c73be-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [<span data-ttu-id="c73be-117">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="c73be-117">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [<span data-ttu-id="c73be-118">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="c73be-118">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
