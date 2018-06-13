---
title: Практическое руководство. Отображение расположенных сбоку вкладок с помощью TabControl
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
ms.openlocfilehash: e145547ba4c8648a765e9507b7f35e50cb15fd82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532465"
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a><span data-ttu-id="f307b-102">Практическое руководство. Отображение расположенных сбоку вкладок с помощью TabControl</span><span class="sxs-lookup"><span data-stu-id="f307b-102">How to: Display Side-Aligned Tabs with TabControl</span></span>
<span data-ttu-id="f307b-103">Свойство <xref:System.Windows.Forms.TabControl.Alignment%2A> элемента <xref:System.Windows.Forms.TabControl> поддерживает вертикальное отображение вкладок (вдоль левой или правой границы элемента управления), в отличие от горизонтального отображения (поперек верхней или нижней области элемента управления).</span><span class="sxs-lookup"><span data-stu-id="f307b-103">The <xref:System.Windows.Forms.TabControl.Alignment%2A> property of <xref:System.Windows.Forms.TabControl> supports displaying tabs vertically (along the left or right edge of the control), as opposed to horizontally (across the top or bottom of the control).</span></span> <span data-ttu-id="f307b-104">Вертикальное отображение по умолчанию бывает неудобным для пользователя, так как свойство <xref:System.Windows.Forms.TabPage.Text%2A> объекта <xref:System.Windows.Forms.TabPage> не отображается на вкладке при включении стилей оформления.</span><span class="sxs-lookup"><span data-stu-id="f307b-104">By default, this vertical display results in a poor user experience, because the <xref:System.Windows.Forms.TabPage.Text%2A> property of the <xref:System.Windows.Forms.TabPage> object does not display in the tab when visual styles are enabled.</span></span> <span data-ttu-id="f307b-105">Также не предусмотрена возможность прямого управления направлением текста на вкладке. Для улучшения взаимодействия с пользователем можно использовать рисование владельцем на <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="f307b-105">There is also no direct way to control the direction of the text within the tab. You can use owner draw on <xref:System.Windows.Forms.TabControl> to improve this experience.</span></span>  
  
 <span data-ttu-id="f307b-106">Ниже описан порядок визуализации вкладок с выравниванием по правому краю, в которых текст располагается слева направо, с помощью функции "рисование владельцем".</span><span class="sxs-lookup"><span data-stu-id="f307b-106">The following procedure shows how to render right-aligned tabs, with the tab text running from left to right, by using the "owner draw" feature.</span></span>  
  
### <a name="to-display-right-aligned-tabs"></a><span data-ttu-id="f307b-107">Отображение вкладок с выравниванием по правому краю</span><span class="sxs-lookup"><span data-stu-id="f307b-107">To display right-aligned tabs</span></span>  
  
1.  <span data-ttu-id="f307b-108">Добавьте элемент <xref:System.Windows.Forms.TabControl> в форму.</span><span class="sxs-lookup"><span data-stu-id="f307b-108">Add a <xref:System.Windows.Forms.TabControl> to your form.</span></span>  
  
2.  <span data-ttu-id="f307b-109">Задайте свойству <xref:System.Windows.Forms.TabControl.Alignment%2A> значение <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="f307b-109">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property to <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
3.  <span data-ttu-id="f307b-110">Присвойте свойству <xref:System.Windows.Forms.TabControl.SizeMode%2A> значение <xref:System.Windows.Forms.TabSizeMode.Fixed> так, чтобы все вкладки имели одинаковую ширину.</span><span class="sxs-lookup"><span data-stu-id="f307b-110">Set the <xref:System.Windows.Forms.TabControl.SizeMode%2A> property to <xref:System.Windows.Forms.TabSizeMode.Fixed>, so that all tabs are the same width.</span></span>  
  
4.  <span data-ttu-id="f307b-111">Для свойства <xref:System.Windows.Forms.TabControl.ItemSize%2A> установите необходимый фиксированный размер вкладок.</span><span class="sxs-lookup"><span data-stu-id="f307b-111">Set the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property to the preferred fixed size for the tabs.</span></span> <span data-ttu-id="f307b-112">Имейте в виду, что свойство <xref:System.Windows.Forms.TabControl.ItemSize%2A> ведет себя так, как если бы вкладки располагались вверху, несмотря на то что они выровнены по правому краю.</span><span class="sxs-lookup"><span data-stu-id="f307b-112">Keep in mind that the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property behaves as though the tabs were on top, although they are right-aligned.</span></span> <span data-ttu-id="f307b-113">Таким образом, чтобы увеличить ширину вкладок, нужно изменить свойство <xref:System.Drawing.Size.Height%2A>, а чтобы сделать их выше, изменить свойство <xref:System.Drawing.Size.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="f307b-113">As a result, in order to make the tabs wider, you must change the <xref:System.Drawing.Size.Height%2A> property, and in order to make them taller, you must change the <xref:System.Drawing.Size.Width%2A> property.</span></span>  
  
     <span data-ttu-id="f307b-114">Для получения оптимальных результатов в примере кода ниже свойство <xref:System.Drawing.Size.Width%2A> имеет значение 25, а <xref:System.Drawing.Size.Height%2A> — значение 100.</span><span class="sxs-lookup"><span data-stu-id="f307b-114">For best result with the code example below, set the <xref:System.Drawing.Size.Width%2A> of the tabs to 25 and the <xref:System.Drawing.Size.Height%2A> to 100.</span></span>  
  
5.  <span data-ttu-id="f307b-115">Задайте свойству <xref:System.Windows.Forms.TabControl.DrawMode%2A> значение <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span><span class="sxs-lookup"><span data-stu-id="f307b-115">Set the <xref:System.Windows.Forms.TabControl.DrawMode%2A> property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span></span>  
  
6.  <span data-ttu-id="f307b-116">Определите обработчик для события <xref:System.Windows.Forms.TabControl.DrawItem> элемента <xref:System.Windows.Forms.TabControl>, выводящий текст слева направо.</span><span class="sxs-lookup"><span data-stu-id="f307b-116">Define a handler for the <xref:System.Windows.Forms.TabControl.DrawItem> event of <xref:System.Windows.Forms.TabControl> that renders the text from left to right.</span></span>  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f307b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f307b-117">See Also</span></span>  
 [<span data-ttu-id="f307b-118">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="f307b-118">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
