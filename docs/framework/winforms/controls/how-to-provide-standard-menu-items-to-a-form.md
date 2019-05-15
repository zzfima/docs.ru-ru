---
title: Практическое руководство. Связывание с формой стандартных элементов меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: a95476ff3d182bf2a56e6527c9ee83c8c56af246
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583642"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="37811-102">Практическое руководство. Связывание с формой стандартных элементов меню</span><span class="sxs-lookup"><span data-stu-id="37811-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="37811-103">С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.</span><span class="sxs-lookup"><span data-stu-id="37811-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="37811-104">Имеется широкая поддержка этой возможности в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37811-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="37811-105">Также см. в разделе [Пошаговое руководство: Создание стандартных пунктов меню для формы](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="37811-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37811-106">Пример</span><span class="sxs-lookup"><span data-stu-id="37811-106">Example</span></span>  
 <span data-ttu-id="37811-107">В примере кода ниже показано, как использовать элемент управления <xref:System.Windows.Forms.MenuStrip> для создания формы, содержащей стандартное меню.</span><span class="sxs-lookup"><span data-stu-id="37811-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="37811-108">Выбранные пункты меню выводятся в элементе управления <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="37811-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="37811-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="37811-109">Compiling the Code</span></span>  
 <span data-ttu-id="37811-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="37811-110">This example requires:</span></span>  
  
- <span data-ttu-id="37811-111">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="37811-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37811-112">См. также</span><span class="sxs-lookup"><span data-stu-id="37811-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="37811-113">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="37811-113">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
