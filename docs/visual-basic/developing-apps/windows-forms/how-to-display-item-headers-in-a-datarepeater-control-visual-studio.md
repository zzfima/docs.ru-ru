---
title: Как выполнить Отображение заголовков элементов в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: eccac1b3b02da41a34d47072be267f6c51a7d490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504565"
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Как выполнить Отображение заголовков элементов в элементе управления DataRepeater (Visual Studio)
Заголовка элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления предоставляется визуальный индикатор, когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> выбран. Когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (по умолчанию), заголовок элемента отображается слева от каждого элемента. Когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, заголовок элемента отображается в верхней части каждого элемента.  
  
 При первоначальном выборе элемента заголовка отображается в цвет, который задается параметром <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> отображается свойство и значок белая стрелка.  
  
> [!NOTE]
>  Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будут видны.  
  
 Когда поле <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> находится в фокусе, цвет заголовка элемента изменяет <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> фоновый цвет и изменения значок со стрелкой на черный. Если данные изменяются, в заголовке элемента отображается символ карандаша.  
  
 Ширина по умолчанию (или высота при <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) элемента заголовка — 15 пикселей. Вы можете изменить ширину, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойство.  
  
> [!NOTE]
>  Если <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойству присваивается значение, которое меньше 11, не будут отображаться значки индикатора в заголовке элемента.  
  
 Заголовки элементов можно скрыть, установив <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> свойства **False**. Когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> присваивается **False**, указывать только, что выбран элемент — Точечная линия по периметру <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  Можно также предоставить свой собственный индикатор выделения, отслеживая <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>Чтобы изменить внешний вид заголовков элементов  
  
1.  В конструкторе Windows Forms, выберите в нижней области таблицы <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
    > [!NOTE]
    >  Необходимо выбрать Нижняя область элемента управления. При выборе области шаблона элемента, в другой набор свойств будет отображаться в окне «Свойства».  
  
2.  В окне «Свойства» используйте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> свойство для изменения цвета заголовков элементов.  
  
    > [!NOTE]
    >  Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будут видны.  
  
3.  Используйте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойство для изменения ширины (или высоты) заголовков элементов.  
  
    > [!NOTE]
    >  Если <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойству присваивается значение, которое меньше 11, не будут отображаться значки индикатора в заголовке элемента.  
  
### <a name="to-hide-item-headers"></a>Чтобы скрыть заголовки элементов  
  
1.  В конструкторе Windows Forms, выберите в нижней области таблицы <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
    > [!NOTE]
    >  Необходимо выбрать Нижняя область элемента управления. При выборе области шаблона элемента, в другой набор свойств будет отображаться в окне «Свойства».  
  
2.  В окне «Свойства» задайте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> свойства **False**.  
  
     При создании записи в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> — флажок установлен, указывать только будет пунктирной линией по периметру <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Изменение макета элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
