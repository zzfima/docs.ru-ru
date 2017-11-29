---
title: "Элемент управления Label (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Label control [Windows Forms]
- labels
- LinkLabel control [Windows Forms]
ms.assetid: 2028bbe3-ffe2-43e8-8ae3-dec759d2ecec
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90a870c71bc7e5d853049d363c27a29d00be3f6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="label-control-windows-forms"></a><span data-ttu-id="9cf44-102">Элемент управления Label (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9cf44-102">Label Control (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="9cf44-103"><xref:System.Windows.Forms.ToolStripLabel> Управления заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9cf44-103">The <xref:System.Windows.Forms.ToolStripLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.Label> control.</span></span> <span data-ttu-id="9cf44-104">Можно использовать <xref:System.Windows.Forms.ToolStripLabel> с другими новыми элементами управления, такие как <xref:System.Windows.Forms.ToolStripDropDown>.</span><span class="sxs-lookup"><span data-stu-id="9cf44-104">You can use the <xref:System.Windows.Forms.ToolStripLabel> with other new controls such as the <xref:System.Windows.Forms.ToolStripDropDown>.</span></span> <span data-ttu-id="9cf44-105">Тем не менее <xref:System.Windows.Forms.Label> элемент управления можно сохранить для обратной совместимости и использования в будущем, если выбрать.</span><span class="sxs-lookup"><span data-stu-id="9cf44-105">However, the <xref:System.Windows.Forms.Label> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="9cf44-106">Windows Forms <xref:System.Windows.Forms.Label> элементы управления используются для отображения текста или изображений, которые не может быть изменена пользователем.</span><span class="sxs-lookup"><span data-stu-id="9cf44-106">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="9cf44-107">Они используются для идентификации объектов в форме — для предоставления описание какие определенный элемент управления будет выполнять при щелчке, например или для отображения сведений в ответ на событие во время выполнения или процесса в приложении.</span><span class="sxs-lookup"><span data-stu-id="9cf44-107">They are used to identify objects on a form—to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="9cf44-108">Поскольку <xref:System.Windows.Forms.Label> элемент управления не может получать фокус, он может также использоваться для создания клавиш доступа для других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9cf44-108">Because the <xref:System.Windows.Forms.Label> control cannot receive focus, it can also be used to create access keys for other controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9cf44-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="9cf44-109">In This Section</span></span>  
 [<span data-ttu-id="9cf44-110">Общие сведения об элементе управления Label</span><span class="sxs-lookup"><span data-stu-id="9cf44-110">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 <span data-ttu-id="9cf44-111">Описывается элемент управления, его основные возможности и свойства.</span><span class="sxs-lookup"><span data-stu-id="9cf44-111">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="9cf44-112">Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cf44-112">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 <span data-ttu-id="9cf44-113">Описывает, как использовать метку для определения сочетания клавиш для другого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9cf44-113">Describes how to use a label to define an access key for another control.</span></span>  
  
 [<span data-ttu-id="9cf44-114">Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cf44-114">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 <span data-ttu-id="9cf44-115">Описывается изменение размера элемента управления label для его заголовка.</span><span class="sxs-lookup"><span data-stu-id="9cf44-115">Explains adjusting the size of a label control for its caption.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9cf44-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="9cf44-116">Reference</span></span>  
 <xref:System.Windows.Forms.Label>  
 <span data-ttu-id="9cf44-117">Описание класса и ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="9cf44-117">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9cf44-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9cf44-118">Related Sections</span></span>  
 [<span data-ttu-id="9cf44-119">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cf44-119">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="9cf44-120">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="9cf44-120">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
