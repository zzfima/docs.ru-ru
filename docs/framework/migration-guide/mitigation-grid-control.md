---
title: "Устранение рисков. Выделение пространства для столбцов со звездочкой в элементе управления \"Сетка\""
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54391538ac0b2daf307cba2f7ceff1984d26b0ce
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a><span data-ttu-id="a4d38-102">Устранение рисков. Выделение пространства для столбцов со звездочкой в элементе управления "Сетка"</span><span class="sxs-lookup"><span data-stu-id="a4d38-102">Mitigation: Grid Control&#39;s Space Allocation to Star-columns</span></span>

<span data-ttu-id="a4d38-103">Начиная с приложений для .NET Framework 4.7, WPF заменяет алгоритм, который использовался в элементе управления <xref:System.Windows.Controls.Grid> для выделения пространства для \*-столбцов.</span><span class="sxs-lookup"><span data-stu-id="a4d38-103">Starting with applications that the .NET Framework 4.7, WPF replaces the algorithm that the <xref:System.Windows.Controls.Grid> control uses to allocate space to \*-columns.</span></span> 

## <a name="whats-changed"></a><span data-ttu-id="a4d38-104">Изменения по сравнению с предыдущей версией</span><span class="sxs-lookup"><span data-stu-id="a4d38-104">What's changed</span></span>

<span data-ttu-id="a4d38-105">Новый алгоритм устраняет некоторые ошибки, присутствующие в старом алгоритме:</span><span class="sxs-lookup"><span data-stu-id="a4d38-105">The new algorithm fixes several bugs present in the old algorithm:</span></span>

1. <span data-ttu-id="a4d38-106">Общее выделенное пространство для столбцов может превышать ширину сетки.</span><span class="sxs-lookup"><span data-stu-id="a4d38-106">Total allocation to columns can exceed the Grid's width.</span></span> <span data-ttu-id="a4d38-107">Это может произойти при выделении пространства для столбца, пропорциональная доля которого меньше его минимального размера.</span><span class="sxs-lookup"><span data-stu-id="a4d38-107">This can occur when allocating space to a column whose proportional share is less than its minimum size.</span></span> <span data-ttu-id="a4d38-108">Алгоритм выделяет минимальный размер, что уменьшает пространство, доступное для других столбцов.</span><span class="sxs-lookup"><span data-stu-id="a4d38-108">The algorithm allocates the minimum size, which decreases the space available to other columns.</span></span> <span data-ttu-id="a4d38-109">Если не осталось \*-столбцов для выделения, общее выделенное пространство будет слишком большим.</span><span class="sxs-lookup"><span data-stu-id="a4d38-109">If there are no \*-columns left to allocate, the total allocation will be too large.</span></span>

1. <span data-ttu-id="a4d38-110">Общее выделенное пространство может быть меньше ширины сетки.</span><span class="sxs-lookup"><span data-stu-id="a4d38-110">Total allocation can fall short of the Grid's width.</span></span> <span data-ttu-id="a4d38-111">Это смежная с первой проблема возникает при выделении пространства для столбца, пропорциональная доля которого больше его максимального размера, когда не остается \*-столбцов для заполнения зарезервированного пространства.</span><span class="sxs-lookup"><span data-stu-id="a4d38-111">This is the dual problem to #1, arising when allocating to a column whose proportional share is greater than its maximum size, with no \*-columns left to take up the slack.</span></span>

1. <span data-ttu-id="a4d38-112">Два \*-столбца могут получить выделенное пространство, непропорциональное их весу.</span><span class="sxs-lookup"><span data-stu-id="a4d38-112">Two \*-columns can receive allocations not proportional to their -weights.</span></span> <span data-ttu-id="a4d38-113">Это более мягкая версия первой или второй проблемы возникает при выделении пространства для *-столбцов A, B и C (в таком порядке), когда пропорциональная доля столбца B нарушает его минимальное (или максимальное) ограничение.</span><span class="sxs-lookup"><span data-stu-id="a4d38-113">This is a milder version of #1/#2, arising when allocating to *-columns A, B, and C (in that order), where B's proportional share violates its min (or max) constraint.</span></span> <span data-ttu-id="a4d38-114">Как показано выше, при этом изменяется место, доступное для столбца C, который получает меньше (или больше) пропорционально выделенного пространства, чем получил столбец A.</span><span class="sxs-lookup"><span data-stu-id="a4d38-114">As above, this changes the space available to column C, who gets less (or more) proportional allocation than A did,</span></span>

1. <span data-ttu-id="a4d38-115">Все столбцы с очень большим весом (свыше 10^298) обрабатываются так, как если бы у них был вес 10^298.</span><span class="sxs-lookup"><span data-stu-id="a4d38-115">Columns with extremely large weights (> 10^298) are all treated as if they had weight 10^298.</span></span> <span data-ttu-id="a4d38-116">Пропорциональные различия между ними (и между столбцами с немного меньшим весом) не учитываются.</span><span class="sxs-lookup"><span data-stu-id="a4d38-116">Proportional differences between them (and between columns with slightly smaller weights) are not honored.</span></span>

1. <span data-ttu-id="a4d38-117">Столбцы с бесконечным весом не обрабатываются правильно.</span><span class="sxs-lookup"><span data-stu-id="a4d38-117">Columns with infinite weights are not handled correctly.</span></span> <span data-ttu-id="a4d38-118">[Фактически невозможно определить вес как бесконечный, но это искусственное ограничение.</span><span class="sxs-lookup"><span data-stu-id="a4d38-118">[Actually you can't set a weight to Infinity, but this is an artificial restriction.</span></span> <span data-ttu-id="a4d38-119">Его обработка кодом выделения была безуспешной.]</span><span class="sxs-lookup"><span data-stu-id="a4d38-119">The allocation code was trying to handle it, but doing a bad job.]</span></span>

1. <span data-ttu-id="a4d38-120">Несколько мелких проблем при предотвращении переполнения, нехватки данных, потери точности и аналогичных проблем с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="a4d38-120">Several minor problems while avoiding overflow, underflow, loss of precision and similar floating-point issues.</span></span>

1. <span data-ttu-id="a4d38-121">Корректировки округления макета неверны при достаточно высоком DPI.</span><span class="sxs-lookup"><span data-stu-id="a4d38-121">Adjustments for layout rounding are incorrect at sufficiently high DPI.</span></span>

<span data-ttu-id="a4d38-122">Новый алгоритм выдает результаты, соответствующие следующим критериям:</span><span class="sxs-lookup"><span data-stu-id="a4d38-122">The new algorithm produces results that meet the following criteria:</span></span>

<span data-ttu-id="a4d38-123">О.</span><span class="sxs-lookup"><span data-stu-id="a4d38-123">A.</span></span> <span data-ttu-id="a4d38-124">Фактическая ширина, назначенная *-столбцу, никогда не меньше его минимальной ширины и не больше максимальной ширины.</span><span class="sxs-lookup"><span data-stu-id="a4d38-124">The actual width assigned to a *-column is never less than its minimum width nor greater than its maximum width.</span></span>

<span data-ttu-id="a4d38-125">Б.</span><span class="sxs-lookup"><span data-stu-id="a4d38-125">B.</span></span> <span data-ttu-id="a4d38-126">Каждому -столбцу, которому не назначена минимальная или максимальная ширина, назначается ширина пропорционально его -весу.</span><span class="sxs-lookup"><span data-stu-id="a4d38-126">Each -column that is not assigned its minimum or maximum width is assigned a width proportional to its -weight.</span></span> <span data-ttu-id="a4d38-127">Точнее, если два столбца объявлены с шириной x и y соответственно, и ни один из них не получил минимальную или максимальную ширину, у фактических значений ширины v и w, присвоенные столбцам, будет та же пропорция: v / w == x / y.</span><span class="sxs-lookup"><span data-stu-id="a4d38-127">To be precise, if two columns are declared with width x and y respectively, and if neither column receives its minimum or maximum width, the actual widths v and w assigned to the columns are in the same proportion: v / w == x / y.</span></span>

<span data-ttu-id="a4d38-128">В.</span><span class="sxs-lookup"><span data-stu-id="a4d38-128">C.</span></span> <span data-ttu-id="a4d38-129">Общая ширина, выделяемая "пропорциональным" \*-столбцам, равна свободному пространству, доступному после выделения для ограниченных столбцов (фиксированных, автоматических и \*-столбцов, которым выделена минимальная или максимальная ширина).</span><span class="sxs-lookup"><span data-stu-id="a4d38-129">The total width allocated to "proportional" \*-columns is equal to the space available after allocating to the constrained columns (fixed, auto, and \*-columns that are allocated their min or max width).</span></span> <span data-ttu-id="a4d38-130">Это значение может быть равно нулю, например, если сумма минимальных значений ширины превышает доступную ширину сетки.</span><span class="sxs-lookup"><span data-stu-id="a4d38-130">This might be zero, for instance if the sum of the minimum widths exceeds the Grid's availbable width.</span></span>

<span data-ttu-id="a4d38-131">Г.</span><span class="sxs-lookup"><span data-stu-id="a4d38-131">D.</span></span> <span data-ttu-id="a4d38-132">Все эти инструкции должны интерпретироваться по отношению к гипотетическому идеальному макету.</span><span class="sxs-lookup"><span data-stu-id="a4d38-132">All these statements are to be interpreted with respect to the "ideal" layout.</span></span> <span data-ttu-id="a4d38-133">Если действует округление макета, фактические значения ширины могут отличаться от идеальных максимум на один пиксель.</span><span class="sxs-lookup"><span data-stu-id="a4d38-133">When layout rounding is in effect, the actual widths can differ from the ideal widths by as much as one pixel.</span></span>

<span data-ttu-id="a4d38-134">Старый алгоритм учитывал (А), но не учитывал другие критерии в случаях, описанных выше.</span><span class="sxs-lookup"><span data-stu-id="a4d38-134">The old algorithm honored (A) but failed to honor the other criteria in the cases outlined above.</span></span>

<span data-ttu-id="a4d38-135">Все сказанное о столбцах и ширине в этом разделе применяется также к строкам и высоте.</span><span class="sxs-lookup"><span data-stu-id="a4d38-135">Everything said about columns and widths in this topic applies as well to rows and heights.</span></span>

## <a name="impact"></a><span data-ttu-id="a4d38-136">Последствия</span><span class="sxs-lookup"><span data-stu-id="a4d38-136">Impact</span></span>

<span data-ttu-id="a4d38-137">Новый алгоритм изменяет фактическую ширину, назначенную \*-столбцам в ряде случаев:</span><span class="sxs-lookup"><span data-stu-id="a4d38-137">The new algorithm changes the actual width assigned to \*-columns in a number of cases:</span></span>

- <span data-ttu-id="a4d38-138">Если один или несколько \*-столбцов также имеют минимальную или максимальную ширину, переопределяющую пропорциональное выделение для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="a4d38-138">When one or more \*-columns also have a minimum or maximum width that overrides the proportional allocation for that column.</span></span> <span data-ttu-id="a4d38-139">(Минимальная ширина может быть производной от явного объявления <xref:System.Windows.FrameworkElement.MinWidth%2A> или неявного минимума, полученного из содержимого столбца.</span><span class="sxs-lookup"><span data-stu-id="a4d38-139">(The minimum width can derive from an explicit <xref:System.Windows.FrameworkElement.MinWidth%2A> declaration, or from an implicit minimum obtained from the column's content.</span></span> <span data-ttu-id="a4d38-140">Максимальная ширина может быть определена только явным образом в объявлении <xref:System.Windows.FrameworkElement.MaxWidth%2A>.)</span><span class="sxs-lookup"><span data-stu-id="a4d38-140">The maximum width can only be defined explicitly, from a <xref:System.Windows.FrameworkElement.MaxWidth%2A> declaration.)</span></span>

- <span data-ttu-id="a4d38-141">Когда один или несколько \*-столбцов объявляют слишком большой \*-вес — более 10^298.</span><span class="sxs-lookup"><span data-stu-id="a4d38-141">When one or more \*-columns declare an extremely large \*-weight, greater than 10^298.</span></span>

- <span data-ttu-id="a4d38-142">Когда \*-веса достаточно отличаются, приводя к нестабильности операций с плавающей запятой (переполнение, нехватка данных, потеря точности).</span><span class="sxs-lookup"><span data-stu-id="a4d38-142">When the \*-weights are sufficiently different to encounter floating-point instability (overflow, underflow, loss of precision).</span></span>

- <span data-ttu-id="a4d38-143">Когда включено округление макета, а действующее значение DPI дисплея достаточно высокое.</span><span class="sxs-lookup"><span data-stu-id="a4d38-143">When layout rounding is enabled, and the effective display DPI is sufficiently high.</span></span>

<span data-ttu-id="a4d38-144">В первых двух случаях значения ширины, создаваемые новым алгоритмом, могут значительно отличаться от созданных старым алгоритмом; в последнем случае разница будет равна максимум одному или двум пикселям.</span><span class="sxs-lookup"><span data-stu-id="a4d38-144">In the first two cases, the widths produced by the new algorithm can be significantly different from those produced by the old algorithm; in the last case, the difference will be at most one or two pixels.</span></span>

## <a name="mitigation"></a><span data-ttu-id="a4d38-145">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="a4d38-145">Mitigation</span></span>

<span data-ttu-id="a4d38-146">По умолчанию приложения, предназначенные для версий .NET Framework 4.7 и выше, будут использовать новый алгоритм, а приложения, предназначенные для .NET Framework 4.6.2 и более ранних версий, — старый алгоритм.</span><span class="sxs-lookup"><span data-stu-id="a4d38-146">By default, apps that target versions of the .NET Framework starting with the .NET Framework 4.7 will use the new algorithm, while apps that target the .NET Framework 4.6.2 or earlier versions will use the old algorithm.</span></span>

<span data-ttu-id="a4d38-147">Чтобы переопределить настройку по умолчанию, используйте следующий параметр конфигурации:</span><span class="sxs-lookup"><span data-stu-id="a4d38-147">To override the default, use the following configuration setting:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

<span data-ttu-id="a4d38-148">Значение true позволяет выбрать старый алгоритм, а false — новый.</span><span class="sxs-lookup"><span data-stu-id="a4d38-148">The value 'true' selects the old algorithm, and 'false' selects the new algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4d38-149">См. также</span><span class="sxs-lookup"><span data-stu-id="a4d38-149">See also</span></span>
[<span data-ttu-id="a4d38-150">Изменения целевой платформы в .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="a4d38-150">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

