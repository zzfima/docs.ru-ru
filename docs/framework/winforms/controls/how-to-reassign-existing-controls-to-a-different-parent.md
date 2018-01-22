---
title: "Практическое руководство. Переназначение существующих элементов управления другим родительским элементам"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26998c002591850c0af3c265ae88b10657343787
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="af9f0-102">Практическое руководство. Переназначение существующих элементов управления другим родительским элементам</span><span class="sxs-lookup"><span data-stu-id="af9f0-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="af9f0-103">Можно назначать существующие в форме элементы управления новому контейнерному элементу управления.</span><span class="sxs-lookup"><span data-stu-id="af9f0-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af9f0-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="af9f0-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="af9f0-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="af9f0-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="af9f0-106">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="af9f0-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="af9f0-107">Переназначение существующих элементов управления другим родительским элементам</span><span class="sxs-lookup"><span data-stu-id="af9f0-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="af9f0-108">Перетащите три элемента управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму.</span><span class="sxs-lookup"><span data-stu-id="af9f0-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="af9f0-109">Расположите их рядом друг с другом, но не выравнивайте.</span><span class="sxs-lookup"><span data-stu-id="af9f0-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="af9f0-110">В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="af9f0-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="af9f0-111">Не перетаскивайте значок на форму.</span><span class="sxs-lookup"><span data-stu-id="af9f0-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="af9f0-112">Переместите указатель мыши к трем элементам управления <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="af9f0-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="af9f0-113">Указатель превратится в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="af9f0-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="af9f0-114">Нажмите и удерживайте кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="af9f0-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="af9f0-115">Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="af9f0-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="af9f0-116">Обведите таким образом три элемента управления <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="af9f0-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="af9f0-117">Отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="af9f0-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="af9f0-118">Теперь три элемента управления <xref:System.Windows.Forms.Button> вставлены в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="af9f0-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9f0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="af9f0-119">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="af9f0-120">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af9f0-120">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="af9f0-121">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="af9f0-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="af9f0-122">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="af9f0-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
