---
title: Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 662343af42f72816a5a673d2cd6d839a5dca9190
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341404"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="1380c-102">Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1380c-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="1380c-103">Windows Forms <xref:System.Windows.Forms.Panel> элементы управления используются для группировки других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1380c-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="1380c-104">Существуют три причины для группировки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1380c-104">There are three reasons to group controls.</span></span> <span data-ttu-id="1380c-105">Первая — визуальная группировка связанных элементов форм для упрощения пользовательского интерфейса; Вторая — программная Группировка, переключателей, например; Последнее — перемещение элементов управления как единое целое во время разработки.</span><span class="sxs-lookup"><span data-stu-id="1380c-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1380c-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="1380c-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1380c-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="1380c-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1380c-108">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1380c-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="1380c-109">Чтобы создать группу элементов управления</span><span class="sxs-lookup"><span data-stu-id="1380c-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="1380c-110">Перетащите <xref:System.Windows.Forms.Panel> управления из **Windows Forms** вкладки панели элементов на форму.</span><span class="sxs-lookup"><span data-stu-id="1380c-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2. <span data-ttu-id="1380c-111">Добавьте другие элементы управления на панель, рисования каждого элемента внутри панели.</span><span class="sxs-lookup"><span data-stu-id="1380c-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="1380c-112">Если у вас есть существующие элементы управления, которые вы хотите включить в панель, можно выбрать все элементы управления, вырезать их в буфер обмена, выберите <xref:System.Windows.Forms.Panel> управления, а затем вставьте их в панель.</span><span class="sxs-lookup"><span data-stu-id="1380c-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="1380c-113">Также можно перетащить их в панель.</span><span class="sxs-lookup"><span data-stu-id="1380c-113">You can also drag them into the panel.</span></span>  
  
3. <span data-ttu-id="1380c-114">(Необязательно) Если вы хотите добавить на панель границу, задайте его <xref:System.Windows.Forms.BorderStyle> свойство.</span><span class="sxs-lookup"><span data-stu-id="1380c-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="1380c-115">Существует три варианта: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, и <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="1380c-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1380c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1380c-116">See also</span></span>

- [<span data-ttu-id="1380c-117">Элемент управления Panel</span><span class="sxs-lookup"><span data-stu-id="1380c-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="1380c-118">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="1380c-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="1380c-119">Практическое руководство. Установка фона панели</span><span class="sxs-lookup"><span data-stu-id="1380c-119">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
