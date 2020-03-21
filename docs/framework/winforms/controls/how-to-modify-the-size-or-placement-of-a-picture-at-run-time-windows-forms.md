---
title: Практическое руководство. Изменение размера или размещения изображения во время выполнения
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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141970"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="26168-102">Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="26168-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="26168-103">Если вы используете <xref:System.Windows.Forms.PictureBox> элемент управления формами Windows <xref:System.Windows.Forms.PictureBox.SizeMode%2A> в форме, вы можете установить свойство на ней:</span><span class="sxs-lookup"><span data-stu-id="26168-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="26168-104">Выровняйте верхний левый угол изображения с верхним левым углом управления</span><span class="sxs-lookup"><span data-stu-id="26168-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="26168-105">Центр изображения в элементе управления</span><span class="sxs-lookup"><span data-stu-id="26168-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="26168-106">Отрегулируйте размер элемента управления, чтобы соответствовать изображению, который он отображает</span><span class="sxs-lookup"><span data-stu-id="26168-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="26168-107">Растянуть любую картинку, которую он отображает, чтобы соответствовать элементу управления</span><span class="sxs-lookup"><span data-stu-id="26168-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="26168-108">Растяжка изображения (особенно в формате bitmap) может привести к потере качества изображения.</span><span class="sxs-lookup"><span data-stu-id="26168-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="26168-109">Metafiles, которые представляют собой списки графических инструкций для рисования изображений во время выполнения, лучше подходят для растяжения, чем bitmaps.</span><span class="sxs-lookup"><span data-stu-id="26168-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="26168-110">Установить свойство SizeMode во время выполнения</span><span class="sxs-lookup"><span data-stu-id="26168-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="26168-111"><xref:System.Windows.Forms.PictureBox.SizeMode%2A> Установить <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (по <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>умолчанию), <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>, , или .</span><span class="sxs-lookup"><span data-stu-id="26168-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="26168-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>означает, что изображение помещается в верхнем левом углу управления; если изображение больше элемента управления, его нижние и правые края обрезаны.</span><span class="sxs-lookup"><span data-stu-id="26168-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="26168-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>означает, что изображение сосредоточено внутри элемента управления; если изображение больше элемента управления, внешние края изображения обрезаны.</span><span class="sxs-lookup"><span data-stu-id="26168-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="26168-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>означает, что размер элемента управления регулируется с размером изображения.</span><span class="sxs-lookup"><span data-stu-id="26168-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="26168-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>является обратным, и означает, что размер изображения регулируется размером элемента управления.</span><span class="sxs-lookup"><span data-stu-id="26168-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="26168-116">В приведенном ниже примере путь, установленный для расположения изображения, представляет собой папку «Мои документы».</span><span class="sxs-lookup"><span data-stu-id="26168-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="26168-117">Это делается, потому что можно предположить, что большинство компьютеров под управлением операционной системы Windows будет включать в себя этот каталог.</span><span class="sxs-lookup"><span data-stu-id="26168-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="26168-118">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="26168-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="26168-119">Приведенный ниже пример предполагает <xref:System.Windows.Forms.PictureBox> форму с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="26168-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26168-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="26168-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="26168-121">Практическое руководство. Загрузка изображения с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="26168-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="26168-122">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="26168-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="26168-123">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="26168-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="26168-124">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="26168-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
