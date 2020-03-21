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
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="4972c-102">Практическое руководство. Определение значка для кнопки элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="4972c-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
> <span data-ttu-id="4972c-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="4972c-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="4972c-104"><xref:System.Windows.Forms.ToolBar>кнопки могут отображать значки внутри них для легкой идентификации пользователями.</span><span class="sxs-lookup"><span data-stu-id="4972c-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="4972c-105">Это достигается путем добавления [изображений в компонент Компонент ImageList,](imagelist-component-windows-forms.md) а затем связывания <xref:System.Windows.Forms.ImageList> компонента с элементом <xref:System.Windows.Forms.ToolBar> управления.</span><span class="sxs-lookup"><span data-stu-id="4972c-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="4972c-106">Установить значок для кнопки панели инструментов программно</span><span class="sxs-lookup"><span data-stu-id="4972c-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="4972c-107">В процедуре мгновенно ели <xref:System.Windows.Forms.ImageList> компонент <xref:System.Windows.Forms.ToolBar> и элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4972c-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="4972c-108">В той же процедуре присвоите изображение компоненту. <xref:System.Windows.Forms.ImageList></span><span class="sxs-lookup"><span data-stu-id="4972c-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="4972c-109">В той же процедуре, назначить <xref:System.Windows.Forms.ImageList> элемент управления для <xref:System.Windows.Forms.ToolBar> управления и назначить свойство <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> отдельных кнопок панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="4972c-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="4972c-110">В следующем примере кода путь, установленный для расположения изображения, является папкой **«Мои документы».**</span><span class="sxs-lookup"><span data-stu-id="4972c-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="4972c-111">Это делается, потому что можно предположить, что большинство компьютеров под управлением операционной системы Windows будет включать в себя этот каталог.</span><span class="sxs-lookup"><span data-stu-id="4972c-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="4972c-112">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="4972c-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="4972c-113">Приведенный ниже пример предполагает <xref:System.Windows.Forms.PictureBox> форму с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="4972c-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="4972c-114">Следуя вышеприведенным шагам, вы должны были написать код, аналогичный тому, который отображается ниже.</span><span class="sxs-lookup"><span data-stu-id="4972c-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4972c-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4972c-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="4972c-116">Практическое руководство. Генерирование событий меню для кнопок элемента управления Toolbar</span><span class="sxs-lookup"><span data-stu-id="4972c-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="4972c-117">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="4972c-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="4972c-118">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="4972c-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
