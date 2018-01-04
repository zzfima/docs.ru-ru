---
title: "Практическое руководство. Блокирование элементов управления в формах Windows Forms."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a0bd0f8dcde95dcbb5ef8fcf398256b6931859c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="ae905-102">Практическое руководство. Блокирование элементов управления в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ae905-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="ae905-103">При разработке пользовательского интерфейса (UI) приложения Windows можно блокировать элементы управления, если они размещены правильно, чтобы случайно не перемещать или изменять их размер, при задании других свойств.</span><span class="sxs-lookup"><span data-stu-id="ae905-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="ae905-104">Кроме того можно блокировать и разблокировать все элементы управления в форме одновременно, что удобно для форм с большим количеством элементов управления, или вы можете разблокировать отдельные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="ae905-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="ae905-105">После размещения всех элементов управления, где требуется в форме, закрепить их все для предотвращения случайного перемещения.</span><span class="sxs-lookup"><span data-stu-id="ae905-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae905-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="ae905-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ae905-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="ae905-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ae905-108">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ae905-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="ae905-109">Чтобы блокировать элемент управления</span><span class="sxs-lookup"><span data-stu-id="ae905-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="ae905-110">В **свойства** окно, нажмите кнопку **заблокирована** свойство и выберите `true`.</span><span class="sxs-lookup"><span data-stu-id="ae905-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="ae905-111">(Дважды щелкните имя переключает параметр свойства.)</span><span class="sxs-lookup"><span data-stu-id="ae905-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="ae905-112">Или щелкните правой кнопкой мыши элемент управления и выберите **блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="ae905-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae905-113">Блокировка элементов управления предотвращает их перетаскивание новый размер или расположение в рабочей области конструирования.</span><span class="sxs-lookup"><span data-stu-id="ae905-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="ae905-114">Тем не менее, можно по-прежнему изменить размер или расположение элементов управления с помощью параметра **свойства** окно или в коде.</span><span class="sxs-lookup"><span data-stu-id="ae905-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="ae905-115">Чтобы заблокировать все элементы управления на форме</span><span class="sxs-lookup"><span data-stu-id="ae905-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="ae905-116">Из **формат** меню, выберите **блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="ae905-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae905-117">Эта команда блокирует размер формы, формы является элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ae905-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="ae905-118">Чтобы разблокировать все заблокированные элементы управления на форме</span><span class="sxs-lookup"><span data-stu-id="ae905-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="ae905-119">Из **формат** меню, выберите **блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="ae905-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="ae905-120">Все ранее заблокированные элементы управления в форме теперь являются разблокирован.</span><span class="sxs-lookup"><span data-stu-id="ae905-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="ae905-121">Чтобы разблокировать отдельные заблокированные элементы управления</span><span class="sxs-lookup"><span data-stu-id="ae905-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="ae905-122">В **свойства** окно, нажмите кнопку **заблокирована** свойство и выберите `false`.</span><span class="sxs-lookup"><span data-stu-id="ae905-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="ae905-123">(Дважды щелкните имя переключает параметр свойства.)</span><span class="sxs-lookup"><span data-stu-id="ae905-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae905-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ae905-124">See Also</span></span>  
 [<span data-ttu-id="ae905-125">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae905-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="ae905-126">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae905-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="ae905-127">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae905-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="ae905-128">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae905-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="ae905-129">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae905-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
