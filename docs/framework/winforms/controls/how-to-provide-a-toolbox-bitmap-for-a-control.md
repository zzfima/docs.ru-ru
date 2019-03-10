---
title: Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: 9072f96bd6e3485e759ed72819229b3f0c33d641
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715962"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="85174-102">Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления</span><span class="sxs-lookup"><span data-stu-id="85174-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="85174-103">Если вы хотите иметь специальный значок для элемента управления отображаются в **элементов**, можно указать образ с помощью <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="85174-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="85174-104">Он представляет собой *атрибут* — особый вид классов, который можно прикреплять к другим классам.</span><span class="sxs-lookup"><span data-stu-id="85174-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="85174-105">Дополнительные сведения об атрибутах см. в разделе [Обзор атрибутов (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) для Visual Basic или [атрибуты (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) для C#.</span><span class="sxs-lookup"><span data-stu-id="85174-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>  
  
 <span data-ttu-id="85174-106">С помощью <xref:System.Drawing.ToolboxBitmapAttribute>, можно указать строку, которая указывает путь и имя файла для точечного рисунка 16 x 16 пикселей.</span><span class="sxs-lookup"><span data-stu-id="85174-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="85174-107">Это изображение появится рядом с элементом управления при добавлении на **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="85174-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="85174-108">Можно также указать <xref:System.Type>, в этом случае загружается растровое изображение, связанное с этим типом.</span><span class="sxs-lookup"><span data-stu-id="85174-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="85174-109">Если задан и <xref:System.Type> и строку, элемент управления ищет ресурс изображения с именем, заданным параметром строки, в сборку, содержащую тип, заданный параметром <xref:System.Type> параметр.</span><span class="sxs-lookup"><span data-stu-id="85174-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="85174-110">Указание растрового изображения для отображения элемента управления на панели элементов</span><span class="sxs-lookup"><span data-stu-id="85174-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="85174-111">Добавить <xref:System.Drawing.ToolboxBitmapAttribute> к объявлению класса элемента управления перед `Class` ключевое слово для visual Basic, а также над объявлением класса для Visual C#.</span><span class="sxs-lookup"><span data-stu-id="85174-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  <span data-ttu-id="85174-112">Перестройте проект.</span><span class="sxs-lookup"><span data-stu-id="85174-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85174-113">Для автоматически созданных элементов управления и компонентов растровое изображение на панели элементов не отображается.</span><span class="sxs-lookup"><span data-stu-id="85174-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="85174-114">Чтобы увидеть растровое изображение, перезагрузите элемент управления с помощью диалогового окна **Выбор элементов панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="85174-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="85174-115">Дополнительные сведения см. в разделе [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="85174-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85174-116">См. также</span><span class="sxs-lookup"><span data-stu-id="85174-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="85174-117">Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="85174-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="85174-118">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="85174-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="85174-119">Общие сведения об атрибутах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85174-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="85174-120">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="85174-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)
