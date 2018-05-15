---
title: Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: d39b0b7ccf95f0da22086a72aa2cee424d7ea8ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="12591-102">Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12591-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="12591-103">В элементах управления Windows Forms обычно отображается текст, связанный с их основной функцией.</span><span class="sxs-lookup"><span data-stu-id="12591-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="12591-104">Например, в элементе управления <xref:System.Windows.Forms.Button> обычно отображается заголовок, указывающий, какое действие выполняется при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="12591-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="12591-105">С помощью свойства <xref:System.Windows.Forms.Control.Text%2A> можно задавать или получать текст для всех элементов управления.</span><span class="sxs-lookup"><span data-stu-id="12591-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="12591-106">Шрифт можно менять с помощью свойства <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="12591-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="12591-107">Также с помощью конструктора можно задавать текст.</span><span class="sxs-lookup"><span data-stu-id="12591-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="12591-108">См. также [как: Создание доступа ключи для Windows Forms элементов управления с помощью конструктора](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [как: задать текст отображается с помощью элемента управления Windows Forms Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [как: определение изображения Отображаемый элементом управления с помощью конструктора Windows Forms](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="12591-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="12591-109">Программное задание текста, отображаемого элементом управления</span><span class="sxs-lookup"><span data-stu-id="12591-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="12591-110">Присвойте свойству <xref:System.Windows.Forms.Control.Text%2A> строку.</span><span class="sxs-lookup"><span data-stu-id="12591-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="12591-111">Чтобы создать подчеркнутую клавишу доступа, поставьте амперсанд (&) перед соответствующей буквой.</span><span class="sxs-lookup"><span data-stu-id="12591-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="12591-112">Присвойте свойству <xref:System.Windows.Forms.Control.Font%2A> объект типа <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="12591-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="12591-113">Для отображения в элементах пользовательского интерфейса, например пунктах меню, специальных символов, которые обычно интерпретируются в них по-другому, можно использовать escape-символ.</span><span class="sxs-lookup"><span data-stu-id="12591-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="12591-114">Например, следующая строка кода задает текст пункта меню & Now For Something Completely Different:</span><span class="sxs-lookup"><span data-stu-id="12591-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="12591-115">См. также</span><span class="sxs-lookup"><span data-stu-id="12591-115">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="12591-116">Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12591-116">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="12591-117">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12591-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
