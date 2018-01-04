---
title: "Практическое руководство. Изменение границ в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e977617f16ef882ad0dcfe1a96a6e8af73d2ae48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="3a7b9-102">Практическое руководство. Изменение границ в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a7b9-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="3a7b9-103">При определении внешнего вида и поведения формы Windows Forms можно выбрать из нескольких стилей границы.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="3a7b9-104">Изменив <xref:System.Windows.Forms.Form.FormBorderStyle%2A> свойство, можно управлять поведением изменения размеров формы.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="3a7b9-105">Кроме того, параметр <xref:System.Windows.Forms.Form.FormBorderStyle%2A> влияет на способ отображения строки заголовка и кнопок, которые на нем могут отображаться.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="3a7b9-106">Для получения дополнительной информации см. <xref:System.Windows.Forms.FormBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="3a7b9-107">В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] предусмотрена расширенная поддержка этой задачи.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-107">There is extensive support for this task in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="3a7b9-108">См. также [как: изменение границ формы Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="3a7b9-108">See also [How to: Change the Borders of Windows Forms Using the Designer](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="3a7b9-109">Установка стиля границ формы Windows Forms программными средствами</span><span class="sxs-lookup"><span data-stu-id="3a7b9-109">To set the border style of Windows Forms programmatically</span></span>  
  
-   <span data-ttu-id="3a7b9-110">Задайте для свойства <xref:System.Windows.Forms.Form.FormBorderStyle%2A> нужный стиль.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="3a7b9-111">В следующем примере кода задает стиль границы формы `DlgBx1` для <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
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
  
     <span data-ttu-id="3a7b9-112">См. также [как: создание диалоговых окон во время разработки](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="3a7b9-112">Also see [How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span></span>  
  
     <span data-ttu-id="3a7b9-113">Кроме того Если выбран стиль границы для формы, которая предоставляет необязательный **свернуть** и **развернуть** кнопки, можно указать, хотите ли вы одной или обеих из этих кнопок, чтобы обеспечить работоспособность.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="3a7b9-114">Эти кнопки полезны в тех случаях, когда требуется точно управлять взаимодействием с пользователем.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="3a7b9-115">**Свернуть** и **развернуть** кнопки включены по умолчанию, и их функции изменяются с помощью **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="3a7b9-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a7b9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3a7b9-116">See Also</span></span>  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [<span data-ttu-id="3a7b9-117">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a7b9-117">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
