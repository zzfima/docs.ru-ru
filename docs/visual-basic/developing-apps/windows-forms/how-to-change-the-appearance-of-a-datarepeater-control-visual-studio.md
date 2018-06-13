---
title: Практическое руководство. Изменение внешнего вида элемента управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
ms.openlocfilehash: 9863d9343ffcecc1e4aae7f6bc16dae39ef76385
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590125"
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>Практическое руководство. Изменение внешнего вида элемента управления DataRepeater (Visual Studio)
Можно изменить внешний вид <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления во время разработки путем задания свойств или во время выполнения путем обработки <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событий.  
  
 Свойства, которые заданы во время разработки, при выборе области шаблона элемента управления будет повторяться для каждого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> во время выполнения. Связанные свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> сам элемент управления будет отображаться во время выполнения остается только если часть контейнера были выявлены (например, если <xref:System.Windows.Forms.Control.Padding%2A> задано большое значение).  
  
 Во время выполнения внешнего свойства могут задаваться на основе от условий. Например в такие приложения, можно изменить цвет фона элемента предупреждать пользователей, когда элемент просрочен. В <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> обработчик событий, если задать свойство в условном операторе например `If…Then`, необходимо также использовать `Else` предложение для указания внешнего вида, если условие не выполнено.  
  
### <a name="to-change-the-appearance-at-design-time"></a>Чтобы изменить внешний вид во время разработки  
  
1.  В конструкторе Windows Forms выберите область шаблона (верхнем) из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
2.  В окне «Свойства» выберите свойство и измените значение. Включать общие свойства, определяющие внешний вид <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, и <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### <a name="to-change-the-appearance-at-run-time"></a>Чтобы изменить внешний вид во время выполнения  
  
1.  В редакторе кода в раскрывающемся списке выберите **DrawItem**.  
  
2.  В <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> обработчика событий, добавьте код для задания свойств:  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>Пример  
 Некоторые стандартные настройки для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления включают возможности отображения строк различными цветами и изменения цвета поля на основе условия. В следующем примере показано, как выполнять эти настройки. В этом примере предполагается, что <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления с привязкой к таблице Products базы данных Northwind.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 Обратите внимание, что для всех этих настроек необходимо предоставить код для задания свойств для обеих сторон условия. Если вы не укажете `Else` условие, во время выполнения могут возникнуть непредсказуемые результаты.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
