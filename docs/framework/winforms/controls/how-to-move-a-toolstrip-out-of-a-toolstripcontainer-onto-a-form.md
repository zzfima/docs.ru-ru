---
title: Практическое руководство. Перемещение элемента ToolStrip из контейнера ToolStripContainer в форму
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: a4b6e3bbc0750ba69607b5c0f96bdbb542aea1be
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424097"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="fec91-102">Практическое руководство. Перемещение элемента ToolStrip из контейнера ToolStripContainer в форму</span><span class="sxs-lookup"><span data-stu-id="fec91-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="fec91-103">Используйте следующую процедуру для перемещения <xref:System.Windows.Forms.ToolStrip> из <xref:System.Windows.Forms.ToolStripContainer> на форму.</span><span class="sxs-lookup"><span data-stu-id="fec91-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fec91-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="fec91-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fec91-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="fec91-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fec91-106">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="fec91-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="fec91-107">Для перемещения ToolStrip из контейнера ToolStripContainer в форму</span><span class="sxs-lookup"><span data-stu-id="fec91-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="fec91-108">Выберите <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="fec91-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="fec91-109">Вырезать <xref:System.Windows.Forms.ToolStrip> , нажав сочетание клавиш CTRL + X, или щелкните правой кнопкой мыши <xref:System.Windows.Forms.ToolStrip> и выберите **Вырезать** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="fec91-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="fec91-110">Выберите форму.</span><span class="sxs-lookup"><span data-stu-id="fec91-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="fec91-111">Вставить <xref:System.Windows.Forms.ToolStrip> , нажав сочетание клавиш CTRL + V, или выберите **вставить** из **изменить** меню.</span><span class="sxs-lookup"><span data-stu-id="fec91-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="fec91-112">Задайте <xref:System.Windows.Forms.ToolStrip.Dock%2A> свойство <xref:System.Windows.Forms.ToolStrip> для **верхней**.</span><span class="sxs-lookup"><span data-stu-id="fec91-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec91-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fec91-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="fec91-114">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fec91-114">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
