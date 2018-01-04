---
title: "Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4582a4bcec1d82651c39be179cbefa2dfc34fa2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="99bac-102">Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="99bac-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="99bac-103">Windows Forms <xref:System.Windows.Forms.Panel> элементы управления используются для группировки других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="99bac-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="99bac-104">Существуют три причины для группировки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="99bac-104">There are three reasons to group controls.</span></span> <span data-ttu-id="99bac-105">Первая — визуальная группировка связанных элементов форм для упрощения пользовательского интерфейса; Вторая — программная Группировка, переключателей, например; третья — перемещение элементов управления как единое целое, во время разработки.</span><span class="sxs-lookup"><span data-stu-id="99bac-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99bac-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="99bac-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="99bac-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="99bac-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="99bac-108">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="99bac-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="99bac-109">Чтобы создать группу элементов управления</span><span class="sxs-lookup"><span data-stu-id="99bac-109">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="99bac-110">Перетащите <xref:System.Windows.Forms.Panel> управления из **Windows Forms** вкладки области элементов на форму.</span><span class="sxs-lookup"><span data-stu-id="99bac-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2.  <span data-ttu-id="99bac-111">Добавьте другие элементы управления в панель путем рисования каждого элемента внутри панели.</span><span class="sxs-lookup"><span data-stu-id="99bac-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="99bac-112">При наличии существующих элементов управления, которые требуется включить в панель, можно выбрать все элементы управления, вырезать их в буфер обмена, выберите <xref:System.Windows.Forms.Panel> управления, а затем вставить их в панель.</span><span class="sxs-lookup"><span data-stu-id="99bac-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="99bac-113">Также можно перетащить их в панель.</span><span class="sxs-lookup"><span data-stu-id="99bac-113">You can also drag them into the panel.</span></span>  
  
3.  <span data-ttu-id="99bac-114">(Необязательно) Если вы хотите добавить границу панели, задайте его <xref:System.Windows.Forms.BorderStyle> свойство.</span><span class="sxs-lookup"><span data-stu-id="99bac-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="99bac-115">Существует три варианта: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, и <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="99bac-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bac-116">См. также</span><span class="sxs-lookup"><span data-stu-id="99bac-116">See Also</span></span>  
 [<span data-ttu-id="99bac-117">Элемент управления Panel</span><span class="sxs-lookup"><span data-stu-id="99bac-117">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="99bac-118">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="99bac-118">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="99bac-119">Практическое руководство. Установка фона панели</span><span class="sxs-lookup"><span data-stu-id="99bac-119">How to: Set the Background of a Panel</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
