---
title: "Практическое руководство. Связывание с формой стандартных элементов меню"
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
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce828cc55e5e83d7129409330e64f1f763dee76b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="ae2e5-102">Практическое руководство. Связывание с формой стандартных элементов меню</span><span class="sxs-lookup"><span data-stu-id="ae2e5-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="ae2e5-103">С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.</span><span class="sxs-lookup"><span data-stu-id="ae2e5-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="ae2e5-104">В [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]эта возможность поддерживается довольно широко.</span><span class="sxs-lookup"><span data-stu-id="ae2e5-104">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="ae2e5-105">См. также [Пошаговое руководство. Создание стандартных пунктов меню для формы](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ae2e5-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae2e5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ae2e5-106">Example</span></span>  
 <span data-ttu-id="ae2e5-107">В примере кода ниже показано, как использовать элемент управления <xref:System.Windows.Forms.MenuStrip> для создания формы, содержащей стандартное меню.</span><span class="sxs-lookup"><span data-stu-id="ae2e5-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="ae2e5-108">Выбранные пункты меню выводятся в элементе управления <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="ae2e5-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae2e5-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ae2e5-109">Compiling the Code</span></span>  
 <span data-ttu-id="ae2e5-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ae2e5-110">This example requires:</span></span>  
  
-   <span data-ttu-id="ae2e5-111">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ae2e5-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="ae2e5-112">Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ae2e5-112">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ae2e5-113">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="ae2e5-113">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="ae2e5-114">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ae2e5-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae2e5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ae2e5-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="ae2e5-116">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="ae2e5-116">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
