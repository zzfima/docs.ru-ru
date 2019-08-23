---
title: Практическое руководство. Задание изображений во время выполнения (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: 99d78a275c8ad8f55d9b0832a794545b65da7e20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917529"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="5080e-102">Практическое руководство. Задание изображений во время выполнения (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5080e-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="5080e-103">Можно программно задать изображение, отображаемое Windows Formsным <xref:System.Windows.Forms.PictureBox> элементом управления.</span><span class="sxs-lookup"><span data-stu-id="5080e-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="5080e-104">Установка рисунка программным способом</span><span class="sxs-lookup"><span data-stu-id="5080e-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="5080e-105">Задайте свойство с помощью <xref:System.Drawing.Image>методакласса. <xref:System.Drawing.Image.FromFile%2A> <xref:System.Windows.Forms.PictureBox.Image%2A></span><span class="sxs-lookup"><span data-stu-id="5080e-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="5080e-106">В приведенном ниже примере путь, заданный для расположения изображения, является папкой "Мои документы".</span><span class="sxs-lookup"><span data-stu-id="5080e-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="5080e-107">Это делается, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут включать этот каталог.</span><span class="sxs-lookup"><span data-stu-id="5080e-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="5080e-108">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="5080e-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="5080e-109">В приведенном ниже примере предполагается, <xref:System.Windows.Forms.PictureBox> что форма с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="5080e-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="5080e-110">Очистка графического изображения</span><span class="sxs-lookup"><span data-stu-id="5080e-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="5080e-111">Сначала освободите память, используемую изображением, а затем очистите изображение.</span><span class="sxs-lookup"><span data-stu-id="5080e-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="5080e-112">Если управление памятью становится проблемой, сборка мусора освободит память позже.</span><span class="sxs-lookup"><span data-stu-id="5080e-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="5080e-113">Дополнительные сведения о том, почему следует использовать <xref:System.Drawing.Image.Dispose%2A> метод таким образом, см. в разделе Очистка неуправляемых [ресурсов](../../../standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="5080e-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="5080e-114">Этот код очистит изображение, даже если изображение было загружено в элемент управления во время разработки.</span><span class="sxs-lookup"><span data-stu-id="5080e-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5080e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5080e-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5080e-116">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="5080e-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="5080e-117">Практическое руководство. Загрузка изображения с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5080e-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="5080e-118">Практическое руководство. Изменение размера или расположения изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="5080e-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="5080e-119">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="5080e-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
