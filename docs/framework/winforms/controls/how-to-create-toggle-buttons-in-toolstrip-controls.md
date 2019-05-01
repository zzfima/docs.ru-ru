---
title: Практическое руководство. Создание переключателей в элементах управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: e688e9a220e6c82caa2d107589b5ca9a1e59e72b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052165"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="a8257-102">Практическое руководство. Создание переключателей в элементах управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a8257-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="a8257-103">Когда пользователь щелкает кнопку-переключатель, он отображается углубленным и остается таковым, пока пользователь не щелкнет кнопку еще раз.</span><span class="sxs-lookup"><span data-stu-id="a8257-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="a8257-104">Для создания переключателя ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="a8257-104">To create a toggling ToolStripButton</span></span>  
  
- <span data-ttu-id="a8257-105">Используйте код, как в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="a8257-105">Use code such as the following code example.</span></span> <span data-ttu-id="a8257-106">Этот код предполагает, что форма содержит <xref:System.Windows.Forms.ToolStrip> элемента управления и что его <xref:System.Windows.Forms.ToolStrip.Items%2A> коллекция содержит <xref:System.Windows.Forms.ToolStripButton> вызывается `toolStripButton1`.</span><span class="sxs-lookup"><span data-stu-id="a8257-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="a8257-107">Также предполагается, что у вас есть обработчик событий, который называется `toolStripButton1_CheckedChanged`.</span><span class="sxs-lookup"><span data-stu-id="a8257-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a8257-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a8257-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="a8257-109">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a8257-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
