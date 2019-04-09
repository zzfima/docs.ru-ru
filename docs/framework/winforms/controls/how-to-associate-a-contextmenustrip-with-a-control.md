---
title: Практическое руководство. Связывание объекта ContextMenuStrip с элементом управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 4e39769621c46ead92076489014f6e0e9dc7863d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122373"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="237cb-102">Практическое руководство. Связывание объекта ContextMenuStrip с элементом управления</span><span class="sxs-lookup"><span data-stu-id="237cb-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="237cb-103">После создания элементов управления и контекстных меню используйте приведенные ниже процедуры для вывода определенного контекстного меню, когда пользователь щелкает элемент управления правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="237cb-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="237cb-104">Эти процедуры связывают объект <xref:System.Windows.Forms.ContextMenuStrip> с формой Windows Forms и элементом управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="237cb-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="237cb-105">Связывание объекта ContextMenuStrip с формой Windows Forms</span><span class="sxs-lookup"><span data-stu-id="237cb-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1.  <span data-ttu-id="237cb-106">Присвойте свойству <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> имя связанного объекта <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="237cb-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="237cb-107">Связывание объекта ContextMenuStrip с элементом управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="237cb-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="237cb-108">Присвойте свойству <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> элемента управления имя связанного объекта <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="237cb-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="237cb-109">Пример</span><span class="sxs-lookup"><span data-stu-id="237cb-109">Example</span></span>  
 <span data-ttu-id="237cb-110">В примере кода ниже создается форма Windows Forms и элемент управления <xref:System.Windows.Forms.ToolStrip>, после чего с ними связывается элемент управления <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="237cb-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="237cb-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="237cb-111">Compiling the Code</span></span>  
 <span data-ttu-id="237cb-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="237cb-112">This example requires:</span></span>  
  
-   <span data-ttu-id="237cb-113">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="237cb-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="237cb-114">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="237cb-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="237cb-115">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="237cb-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="237cb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="237cb-116">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="237cb-117">Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="237cb-117">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="237cb-118">Элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="237cb-118">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
