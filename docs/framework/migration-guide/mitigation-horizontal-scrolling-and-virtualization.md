---
title: "Устранение рисков. Горизонтальная прокрутка и виртуализация | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bafd9b-a3b3-4f92-8241-2aad254fb1a9
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 37c60fd8a3e3e4e44dc00e278f6edafcdd766c03
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-horizontal-scrolling-and-virtualization"></a>Устранение рисков. Горизонтальная прокрутка и виртуализация
Это изменение относится к элементу управления <xref:System.Windows.Controls.ItemsControl>, который выполняет собственную виртуализацию в направлении, перпендикулярном основному направлению прокрутки. (Важнейшим примером является элемент управления <xref:System.Windows.Controls.DataGrid>, у которого <xref:System.Windows.Controls.DataGrid.EnableColumnVirtualization%2A> имеет значение `true`.)  Результат некоторых операций горизонтальной прокрутки был изменен для получения результатов, которые являются более интуитивно понятными и более подобными результатам сопоставимых вертикальных операций.  К конкретным операциям относятся **Прокрутка на месте** и **К правому краю**, с использованием имен из меню, открываемого щелчком правой кнопкой мыши по горизонтальной полосе прокрутки.  Обе они вычисляют предполагаемое смещение и вызывают <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.  После прокрутки к новой позиции может измениться значение "на месте" или "правый край" может измениться, поскольку новое девиртуализированное содержимое изменяет значение свойства <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A?displayProperty=fullName>.  
  
## <a name="description-of-the-change"></a>Описание изменения  
 В версиях до [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] операция прокрутки просто использует смещение кандидатов, несмотря на то, что оно может оказаться больше не "на месте" или на "правом краю".  Его результаты проявляются в виде "подпрыгивания" бегунка прокрутки. Лучше всего это проиллюстрировать на примере.  Предположим, что элемент управления <xref:System.Windows.Controls.DataGrid> имеет параметр <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> со значением 1000 и параметр <xref:System.Windows.FrameworkElement.Width%2A> со значением 200.  При прокрутке "К правому краю" используется смещение кандидата 1000 – 200 = 800.  В процессе прокрутки к этому смещению девиртуализируются новые столбцы. Предположим, что они очень широкие, и теперь свойство <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> получает значение 2000.  Прокрутка заканчивается при <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A>= 800, и бегунок "отпрыгивает" обратно почти в середину полосы прокрутки, а точнее на позицию 40% (800/2000).  
  
 Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], в такой ситуации пересчитывается новое смещение кандидата. (Так уже работает вертикальная прокрутка.)  
  
## <a name="impact"></a>Последствия  
 Это поведение стало более прогнозируемым и интуитивно понятным для конечного пользователя, но изменение может повлиять на те приложения, которые ожидают конкретных значений свойства <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> после горизонтальной прокрутки, вызванной действиями пользователя или прямым вызовом <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.  
  
## <a name="mitigation"></a>Уменьшение  
 Нужно изменить приложения, использующие прогнозируемое значение для <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>, чтобы они получали фактическое значение (а также значение <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>) после любой горизонтальной прокрутки, при которой <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> может измениться из-за девиртуализации.  
  
## <a name="see-also"></a>См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
