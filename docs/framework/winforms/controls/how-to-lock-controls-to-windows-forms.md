---
title: Практическое руководство. Прикрепление элементов управления в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: 9eb762a9691a6127e2419f9ddc25f3010d3383fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966528"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="cfb1f-102">Практическое руководство. Прикрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfb1f-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="cfb1f-103">При проектировании пользовательского интерфейса приложения Windows можно заблокировать элементы управления после их правильного позиционирования, чтобы случайно не перемещать их или изменять их размер при настройке других свойств.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

 <span data-ttu-id="cfb1f-104">Кроме того, можно одновременно заблокировать и разблокировать все элементы управления в форме, что полезно для форм с множеством элементов управления или разблокирование отдельных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="cfb1f-105">После размещения всех элементов управления в форме следует заблокировать их все на месте, чтобы предотвратить ошибочное перемещение.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="cfb1f-106">Блокировка элемента управления</span><span class="sxs-lookup"><span data-stu-id="cfb1f-106">To lock a control</span></span>

1. <span data-ttu-id="cfb1f-107">В окне **Свойства** Щелкните заблокированное свойство и выберите `true`.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-107">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="cfb1f-108">(Двойной щелчок по имени переключает параметр свойства.)</span><span class="sxs-lookup"><span data-stu-id="cfb1f-108">(Double-clicking the name toggles the property setting.)</span></span>

     <span data-ttu-id="cfb1f-109">Также можно щелкнуть элемент управления правой кнопкой мыши и выбрать пункт **Блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cfb1f-110">Блокировка элементов управления предотвращает их перетаскивание на новый размер или расположение в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="cfb1f-111">Однако размер или расположение элементов управления по-прежнему можно изменить с помощью окна « **Свойства** » или в коде.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="cfb1f-112">Блокировка всех элементов управления в форме</span><span class="sxs-lookup"><span data-stu-id="cfb1f-112">To lock all the controls on a form</span></span>

1. <span data-ttu-id="cfb1f-113">В меню **Формат** выберите пункт **Блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-113">From the **Format** menu, choose **Lock Controls**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cfb1f-114">Эта команда также блокирует размер формы, поскольку форма является элементом управления.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="cfb1f-115">Разблокирование всех заблокированных элементов управления в форме</span><span class="sxs-lookup"><span data-stu-id="cfb1f-115">To unlock all locked controls on a form</span></span>

1. <span data-ttu-id="cfb1f-116">В меню **Формат** выберите пункт **Блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-116">From the **Format** menu, choose **Lock Controls**.</span></span>

     <span data-ttu-id="cfb1f-117">Все ранее заблокированные элементы управления в форме теперь разблокированы.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="cfb1f-118">Разблокирование заблокированных элементов управления по отдельности</span><span class="sxs-lookup"><span data-stu-id="cfb1f-118">To unlock locked controls individually</span></span>

1. <span data-ttu-id="cfb1f-119">В окне **Свойства** Щелкните заблокированное свойство и выберите `false`.</span><span class="sxs-lookup"><span data-stu-id="cfb1f-119">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="cfb1f-120">(Двойной щелчок по имени переключает параметр свойства.)</span><span class="sxs-lookup"><span data-stu-id="cfb1f-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="cfb1f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cfb1f-121">See also</span></span>

- [<span data-ttu-id="cfb1f-122">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfb1f-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="cfb1f-123">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfb1f-123">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="cfb1f-124">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfb1f-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="cfb1f-125">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfb1f-125">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="cfb1f-126">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfb1f-126">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
