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
ms.openlocfilehash: 3698d2fdbd0375d0a154d6ecea3a248b31da2aeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537525"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления
Если вы хотите иметь специальный значок для элемента управления отображаются в **элементов**, можно указать конкретный образ с помощью <xref:System.Drawing.ToolboxBitmapAttribute>. Он представляет собой *атрибут* — особый вид классов, который можно прикреплять к другим классам. Дополнительные сведения об атрибутах см. в разделе [не в СБОРКЕ: Обзор атрибутов в Visual Basic](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f) для Visual Basic и [атрибуты](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) для Visual C#.  
  
 С помощью <xref:System.Drawing.ToolboxBitmapAttribute>, можно указать строку, которая указывает путь и имя файла для точечного рисунка 16 x 16 пикселей. Это изображение появится рядом с элементом управления при добавлении на **панель элементов**. Можно также указать <xref:System.Type>, в этом случае загружается растровое изображение, связанное с этим типом. Если заданы оба <xref:System.Type> и строку, элемент управления выполняет поиск ресурса изображения с именем, указанным в параметре строки в сборке, содержащей тип, заданный параметром <xref:System.Type> параметр.  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>Указание растрового изображения для отображения элемента управления на панели элементов  
  
1.  Добавить <xref:System.Drawing.ToolboxBitmapAttribute> объявление класса элемента управления перед `Class` ключевое слово для visual Basic и выше объявления класса для Visual C#.  
  
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
  
2.  Перестройте проект.  
  
    > [!NOTE]
    >  Для автоматически созданных элементов управления и компонентов растровое изображение на панели элементов не отображается. Чтобы увидеть растровое изображение, перезагрузите элемент управления с помощью диалогового окна **Выбор элементов панели элементов**. Дополнительные сведения см. в разделе [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [Создание элементов управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Атрибуты (Visual Basic)](~/docs/visual-basic/language-reference/attributes.md)  
 [Атрибуты](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
