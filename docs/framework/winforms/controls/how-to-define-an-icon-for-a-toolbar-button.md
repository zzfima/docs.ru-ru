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
ms.openlocfilehash: 2b85f734a5f8b31531cfe48f87681d98304db09b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929634"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="d5ded-102">Практическое руководство. Определение значка для кнопки элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="d5ded-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
> <span data-ttu-id="d5ded-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="d5ded-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="d5ded-104"><xref:System.Windows.Forms.ToolBar>кнопки могут отображать значки в них для простоты идентификации пользователями.</span><span class="sxs-lookup"><span data-stu-id="d5ded-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="d5ded-105">Это достигается путем добавления изображений в компонент [компонента ImageList](imagelist-component-windows-forms.md) и последующего связывания <xref:System.Windows.Forms.ImageList> компонента с <xref:System.Windows.Forms.ToolBar> элементом управления.</span><span class="sxs-lookup"><span data-stu-id="d5ded-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="d5ded-106">Установка значка для кнопки панели инструментов программными средствами</span><span class="sxs-lookup"><span data-stu-id="d5ded-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="d5ded-107">В процедуре создайте экземпляр <xref:System.Windows.Forms.ImageList> компонента <xref:System.Windows.Forms.ToolBar> и элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d5ded-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="d5ded-108">В той же процедуре назначьте образ <xref:System.Windows.Forms.ImageList> компоненту.</span><span class="sxs-lookup"><span data-stu-id="d5ded-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="d5ded-109">В той же процедуре назначьте <xref:System.Windows.Forms.ImageList> элемент <xref:System.Windows.Forms.ToolBar> управления элементу управления и назначьте <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> свойство отдельных кнопок панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="d5ded-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="d5ded-110">В следующем примере кода путь, заданный для расположения изображения, является папкой " **Мои документы** ".</span><span class="sxs-lookup"><span data-stu-id="d5ded-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="d5ded-111">Это делается, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать этот каталог.</span><span class="sxs-lookup"><span data-stu-id="d5ded-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="d5ded-112">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="d5ded-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="d5ded-113">В приведенном ниже примере предполагается, <xref:System.Windows.Forms.PictureBox> что форма с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="d5ded-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="d5ded-114">Выполнив приведенные выше действия, необходимо написать код, аналогичный показанному ниже.</span><span class="sxs-lookup"><span data-stu-id="d5ded-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d5ded-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d5ded-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="d5ded-116">Практическое руководство. События меню триггера для кнопок панели инструментов</span><span class="sxs-lookup"><span data-stu-id="d5ded-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="d5ded-117">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="d5ded-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="d5ded-118">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="d5ded-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
