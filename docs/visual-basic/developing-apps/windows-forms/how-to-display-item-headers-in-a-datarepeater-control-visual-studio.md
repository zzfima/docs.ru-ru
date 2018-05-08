---
title: Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: 07f6a7e06c5b1e91597ab6b6d816407a2c172278
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater (Visual Studio)
Заголовок элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления предоставляется визуальный индикатор, когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> выбран. Когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (по умолчанию), заголовок элемента отображается слева от каждого элемента. Когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, заголовок элемента отображается в верхней части каждого элемента.  
  
 При первоначальном выборе заголовок элемента отображается цветом, который задается параметром <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> отображаются свойства и белый значок со стрелкой.  
  
> [!NOTE]
>  Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будут видны.  
  
 Когда поле <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> находится в фокусе, цвет заголовка элемента изменяет <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> фоновый цвет и изменения значок со стрелкой в черный цвет. Если данные изменяются, в заголовке элементов отображается символ карандаша.  
  
 Ширина по умолчанию (или высоту при <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) элемента заголовка — 15 пикселей. Можно изменить, задав ширину <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойство.  
  
> [!NOTE]
>  Если <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойству присвоено значение, которое меньше 11, не будут отображаться значки индикатора в заголовке элементов.  
  
 Заголовки элементов можно скрыть, установив <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> свойства **False**. Когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> равно **False**, единственное свидетельство того, что выбран элемент — пунктирная линия по периметру <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  Можно также предоставить свой собственный индикатор выделения, наблюдение за <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>Чтобы изменить внешний вид заголовков элементов  
  
1.  В конструкторе Windows Forms выберите нижнюю область этого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
    > [!NOTE]
    >  Необходимо выбрать Нижняя область элемента управления. При выборе области шаблона элемента иным набором свойств будет отображаться в окне «Свойства».  
  
2.  В окне «Свойства» используйте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> свойство для изменения цвета заголовков элементов.  
  
    > [!NOTE]
    >  Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будут видны.  
  
3.  Используйте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойство для изменения ширины (или высоты) заголовков элементов.  
  
    > [!NOTE]
    >  Если <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойству присвоено значение, которое меньше 11, не будут отображаться значки индикатора в заголовке элементов.  
  
### <a name="to-hide-item-headers"></a>Чтобы скрыть заголовки элементов  
  
1.  В конструкторе Windows Forms выберите нижнюю область этого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
    > [!NOTE]
    >  Необходимо выбрать Нижняя область элемента управления. При выборе области шаблона элемента иным набором свойств будет отображаться в окне «Свойства».  
  
2.  В окне свойств задайте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> свойства **False**.  
  
     При создании записи в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> — флажок установлен, указывать только будет пунктирная линия по периметру <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Изменение структуры элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
