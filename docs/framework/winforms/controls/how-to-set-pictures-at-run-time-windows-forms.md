---
title: Практическое руководство. Установка изображений во время выполнения
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
ms.openlocfilehash: cd599ac7e07b5210f8bcff1ffbc76b3d9ee563d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182119"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="13d1d-102">Практическое руководство. Установка изображений во время выполнения (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="13d1d-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="13d1d-103">Можно программно установить изображение, отображаемые элементом управления формами <xref:System.Windows.Forms.PictureBox> Windows.</span><span class="sxs-lookup"><span data-stu-id="13d1d-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="13d1d-104">Установить картинку программно</span><span class="sxs-lookup"><span data-stu-id="13d1d-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="13d1d-105">Установите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство <xref:System.Drawing.Image.FromFile%2A> методом <xref:System.Drawing.Image> класса.</span><span class="sxs-lookup"><span data-stu-id="13d1d-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="13d1d-106">В приведенном ниже примере путь, установленный для расположения изображения, представляет собой папку «Мои документы».</span><span class="sxs-lookup"><span data-stu-id="13d1d-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="13d1d-107">Это делается, потому что можно предположить, что большинство компьютеров под управлением операционной системы Windows будет включать в себя этот каталог.</span><span class="sxs-lookup"><span data-stu-id="13d1d-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="13d1d-108">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="13d1d-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="13d1d-109">Приведенный ниже пример предполагает <xref:System.Windows.Forms.PictureBox> форму с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="13d1d-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="13d1d-110">Чтобы очистить графический</span><span class="sxs-lookup"><span data-stu-id="13d1d-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="13d1d-111">Во-первых, отпустите память, используемую изображением, а затем очистите графику.</span><span class="sxs-lookup"><span data-stu-id="13d1d-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="13d1d-112">Сбор мусора высвободит память позже, если управление памятью станет проблемой.</span><span class="sxs-lookup"><span data-stu-id="13d1d-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
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
    > <span data-ttu-id="13d1d-113">Для получения дополнительной информации <xref:System.Drawing.Image.Dispose%2A> о том, почему вы должны использовать метод таким образом, см. [Очистка неуправляемых ресурсов.](../../../standard/garbage-collection/unmanaged.md)</span><span class="sxs-lookup"><span data-stu-id="13d1d-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="13d1d-114">Этот код очистит изображение, даже если графический был загружен в управление во время проектирования.</span><span class="sxs-lookup"><span data-stu-id="13d1d-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d1d-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13d1d-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="13d1d-116">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="13d1d-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="13d1d-117">Практическое руководство. Загрузка изображения с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="13d1d-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="13d1d-118">Практическое руководство. Изменение размера или размещения изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="13d1d-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="13d1d-119">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="13d1d-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
