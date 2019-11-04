---
title: Практическое руководство. Блокирование элементов управления в формах Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d157ddc8be4b5fa0057241b562e76b566e8dad99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458343"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="db62e-102">Руководство. Блокировка элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db62e-102">How to: Lock controls to Windows Forms</span></span>

<span data-ttu-id="db62e-103">При проектировании пользовательского интерфейса приложения Windows можно заблокировать элементы управления после их правильного позиционирования, чтобы случайно не перемещать их или изменять их размер при настройке других свойств.</span><span class="sxs-lookup"><span data-stu-id="db62e-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

<span data-ttu-id="db62e-104">Кроме того, можно одновременно заблокировать и разблокировать все элементы управления в форме, что полезно для форм с множеством элементов управления или разблокирование отдельных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="db62e-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="db62e-105">После размещения всех элементов управления в форме следует заблокировать их все на месте, чтобы предотвратить ошибочное перемещение.</span><span class="sxs-lookup"><span data-stu-id="db62e-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="db62e-106">Блокировка элемента управления</span><span class="sxs-lookup"><span data-stu-id="db62e-106">To lock a control</span></span>

<span data-ttu-id="db62e-107">В окне **Свойства** в Visual Studio выберите свойство **заблокировано** и выберите **значение true**.</span><span class="sxs-lookup"><span data-stu-id="db62e-107">In the **Properties** window of Visual Studio, select the **Locked** property and then select **true**.</span></span> <span data-ttu-id="db62e-108">(Двойной щелчок по имени переключает параметр свойства.)</span><span class="sxs-lookup"><span data-stu-id="db62e-108">(Double-clicking the name toggles the property setting.)</span></span>

<span data-ttu-id="db62e-109">Также можно щелкнуть элемент управления правой кнопкой мыши и выбрать пункт **Блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="db62e-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="db62e-110">Блокировка элементов управления предотвращает их перетаскивание на новый размер или расположение в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="db62e-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="db62e-111">Однако размер или расположение элементов управления по-прежнему можно изменить с помощью окна « **Свойства** » или в коде.</span><span class="sxs-lookup"><span data-stu-id="db62e-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="db62e-112">Блокировка всех элементов управления в форме</span><span class="sxs-lookup"><span data-stu-id="db62e-112">To lock all the controls on a form</span></span>

<span data-ttu-id="db62e-113">В меню **Формат** выберите пункт **Блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="db62e-113">From the **Format** menu, choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="db62e-114">Эта команда также блокирует размер формы, поскольку форма является элементом управления.</span><span class="sxs-lookup"><span data-stu-id="db62e-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="db62e-115">Разблокирование всех заблокированных элементов управления в форме</span><span class="sxs-lookup"><span data-stu-id="db62e-115">To unlock all locked controls on a form</span></span>

<span data-ttu-id="db62e-116">В меню **Формат** выберите пункт **Блокировать элементы управления**.</span><span class="sxs-lookup"><span data-stu-id="db62e-116">From the **Format** menu, choose **Lock Controls**.</span></span>

<span data-ttu-id="db62e-117">Все ранее заблокированные элементы управления в форме теперь разблокированы.</span><span class="sxs-lookup"><span data-stu-id="db62e-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="db62e-118">Разблокирование заблокированных элементов управления по отдельности</span><span class="sxs-lookup"><span data-stu-id="db62e-118">To unlock locked controls individually</span></span>

<span data-ttu-id="db62e-119">В окне **Свойства** выберите свойство **заблокировано** и нажмите кнопку **false**.</span><span class="sxs-lookup"><span data-stu-id="db62e-119">In the **Properties** window, select the **Locked** property and then select **false**.</span></span> <span data-ttu-id="db62e-120">(Двойной щелчок по имени переключает параметр свойства.)</span><span class="sxs-lookup"><span data-stu-id="db62e-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="db62e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="db62e-121">See also</span></span>

- [<span data-ttu-id="db62e-122">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db62e-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="db62e-123">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db62e-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="db62e-124">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db62e-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="db62e-125">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db62e-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
