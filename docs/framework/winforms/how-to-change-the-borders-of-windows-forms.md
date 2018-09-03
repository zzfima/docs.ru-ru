---
title: Практическое руководство. Изменение границ в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: e04234b4f2f18738567c3f9846d8ae0c94780fcb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482754"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="dd22b-102">Практическое руководство. Изменение границ в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd22b-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="dd22b-103">При определении внешнего вида и поведения формы Windows Forms можно выбрать из нескольких стилей границы.</span><span class="sxs-lookup"><span data-stu-id="dd22b-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="dd22b-104">Изменив <xref:System.Windows.Forms.Form.FormBorderStyle%2A> свойство, можно управлять поведением изменения размеров формы.</span><span class="sxs-lookup"><span data-stu-id="dd22b-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="dd22b-105">Кроме того, параметр <xref:System.Windows.Forms.Form.FormBorderStyle%2A> влияет на способ отображения строки заголовка и кнопок, которые на нем могут отображаться.</span><span class="sxs-lookup"><span data-stu-id="dd22b-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="dd22b-106">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.FormBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="dd22b-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="dd22b-107">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="dd22b-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="dd22b-108">См. также [как: изменение границ в Windows Forms с помощью конструктора](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="dd22b-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="dd22b-109">Установка стиля границ формы Windows Forms программными средствами</span><span class="sxs-lookup"><span data-stu-id="dd22b-109">To set the border style of Windows Forms programmatically</span></span>  
  
-   <span data-ttu-id="dd22b-110">Задайте для свойства <xref:System.Windows.Forms.Form.FormBorderStyle%2A> нужный стиль.</span><span class="sxs-lookup"><span data-stu-id="dd22b-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="dd22b-111">В следующем примере кода задает стиль границы формы `DlgBx1` для <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span><span class="sxs-lookup"><span data-stu-id="dd22b-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     <span data-ttu-id="dd22b-112">Также см. в разделе [как: создание диалоговых окон во время разработки](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="dd22b-112">Also see [How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span></span>  
  
     <span data-ttu-id="dd22b-113">Кроме того Если выбран стиль границы для формы, которая предоставляет необязательный **свернуть** и **развернуть** кнопок, можно указать, хотите ли вы один или оба эти кнопки для его функционирования.</span><span class="sxs-lookup"><span data-stu-id="dd22b-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="dd22b-114">Эти кнопки полезны в тех случаях, когда требуется точно управлять взаимодействием с пользователем.</span><span class="sxs-lookup"><span data-stu-id="dd22b-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="dd22b-115">**Свернуть** и **развернуть** кнопки включены по умолчанию, и их функции изменяются с помощью **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="dd22b-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd22b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dd22b-116">See Also</span></span>  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [<span data-ttu-id="dd22b-117">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd22b-117">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
