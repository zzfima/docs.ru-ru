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
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736034"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="5c9ba-102">Практическое руководство. Изменение размера или размещения изображения во время выполнения (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5c9ba-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="5c9ba-103">Если в форме используется элемент управления <xref:System.Windows.Forms.PictureBox> Windows Forms, можно задать для него свойство <xref:System.Windows.Forms.PictureBox.SizeMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="5c9ba-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="5c9ba-104">Выровняйте верхний левый угол изображения по левому верхнему углу элемента управления</span><span class="sxs-lookup"><span data-stu-id="5c9ba-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="5c9ba-105">Центрирование рисунка внутри элемента управления</span><span class="sxs-lookup"><span data-stu-id="5c9ba-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="5c9ba-106">Настройка размера элемента управления в соответствии с отображаемым изображением</span><span class="sxs-lookup"><span data-stu-id="5c9ba-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="5c9ba-107">Растяжение всех рисунков, которые отображаются в соответствии с элементом управления</span><span class="sxs-lookup"><span data-stu-id="5c9ba-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="5c9ba-108">Растяжение изображения (особенно в формате точечного рисунка) может привести к ухудшению качества изображения.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="5c9ba-109">Метафайлы, представляющие собой списки графических инструкций для рисования изображений во время выполнения, лучше подходят для растяжения по сравнению с точечными рисунками.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="5c9ba-110">Задание свойства Сиземоде во время выполнения</span><span class="sxs-lookup"><span data-stu-id="5c9ba-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="5c9ba-111">Задайте для <xref:System.Windows.Forms.PictureBox.SizeMode%2A> значение <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (по умолчанию), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>или <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="5c9ba-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> означает, что изображение помещается в левый верхний угол элемента управления; Если изображение больше элемента управления, его нижний и правый края обрезаются.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="5c9ba-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> означает, что изображение центрируется в элементе управления; Если изображение больше элемента управления, внешние края рисунка обрезаются.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="5c9ba-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> означает, что размер элемента управления изменяется в соответствии с размером изображения.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="5c9ba-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> является обратным и означает, что размер изображения корректируется до размера элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="5c9ba-116">В приведенном ниже примере путь, заданный для расположения изображения, является папкой "Мои документы".</span><span class="sxs-lookup"><span data-stu-id="5c9ba-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="5c9ba-117">Это делается, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать этот каталог.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="5c9ba-118">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="5c9ba-119">В приведенном ниже примере предполагается, что форма с уже добавленным элементом управления <xref:System.Windows.Forms.PictureBox>.</span><span class="sxs-lookup"><span data-stu-id="5c9ba-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5c9ba-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c9ba-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="5c9ba-121">Практическое руководство. Загрузка изображения с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5c9ba-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="5c9ba-122">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="5c9ba-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="5c9ba-123">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="5c9ba-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="5c9ba-124">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="5c9ba-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
