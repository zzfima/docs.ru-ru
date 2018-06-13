---
title: Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: 9e6e114e0a9d7e5e9c17ba21ef941703cd108784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534778"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="e8874-102">Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e8874-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="e8874-103">Если вы используете Windows Forms <xref:System.Windows.Forms.PictureBox> элемента управления в форме, можно задать <xref:System.Windows.Forms.PictureBox.SizeMode%2A> свойства:</span><span class="sxs-lookup"><span data-stu-id="e8874-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
-   <span data-ttu-id="e8874-104">Выравнивание верхнего левого угла изображения с верхнего левого угла элемента управления</span><span class="sxs-lookup"><span data-stu-id="e8874-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
-   <span data-ttu-id="e8874-105">Центрировать изображение в элементе управления</span><span class="sxs-lookup"><span data-stu-id="e8874-105">Center the picture within the control</span></span>  
  
-   <span data-ttu-id="e8874-106">Изменить размер элемента управления по размеру изображения, которые в нем отображаются</span><span class="sxs-lookup"><span data-stu-id="e8874-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
-   <span data-ttu-id="e8874-107">Изменять размеры рисунка в соответствии с размерами элемента управления</span><span class="sxs-lookup"><span data-stu-id="e8874-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="e8874-108">Растяжение рисунка (особенно в формат растрового изображения) может привести к ухудшению качества изображения.</span><span class="sxs-lookup"><span data-stu-id="e8874-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="e8874-109">Метафайлы, в которых перечислены инструкции для создания изображений во время выполнения, лучше подходят для растяжения границ, чем растровые изображения.</span><span class="sxs-lookup"><span data-stu-id="e8874-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="e8874-110">Чтобы задать свойства SizeMode во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e8874-110">To set the SizeMode property at run time</span></span>  
  
1.  <span data-ttu-id="e8874-111">Задать <xref:System.Windows.Forms.PictureBox.SizeMode%2A> для <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (по умолчанию), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, или <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="e8874-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="e8874-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> означает, что изображение размещается в левом верхнем углу элемента управления; Если изображение больше, чем элемент управления, его нижняя и правая границы обрезаются.</span><span class="sxs-lookup"><span data-stu-id="e8874-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="e8874-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> означает, что изображение по центру элемента управления; Если изображение больше, чем элемент управления, его внешние границы обрезаются.</span><span class="sxs-lookup"><span data-stu-id="e8874-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="e8874-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> означает, что размер элемента управления размер изображения.</span><span class="sxs-lookup"><span data-stu-id="e8874-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="e8874-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> является обратным и означает, что размер изображения размер элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e8874-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="e8874-116">В следующем примере в расположение образа выбрана папка «Мои документы».</span><span class="sxs-lookup"><span data-stu-id="e8874-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="e8874-117">Эта операция необходима, поскольку можно предположить, что большинство компьютеров под управлением операционной системы Windows включает этот каталог.</span><span class="sxs-lookup"><span data-stu-id="e8874-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="e8874-118">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="e8874-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="e8874-119">В приведенном ниже примере предполагается наличие формы с <xref:System.Windows.Forms.PictureBox> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="e8874-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e8874-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e8874-120">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="e8874-121">Практическое руководство. Загрузка изображения с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e8874-121">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [<span data-ttu-id="e8874-122">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="e8874-122">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="e8874-123">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e8874-123">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="e8874-124">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="e8874-124">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
