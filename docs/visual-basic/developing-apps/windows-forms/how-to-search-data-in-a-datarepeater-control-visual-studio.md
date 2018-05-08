---
title: Практическое руководство. Поиск данных в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 689990ee125c85c3151a4e965b619fde068d220e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a>Практическое руководство. Поиск данных в элементе управления DataRepeater (Visual Studio)
При использовании <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления, который содержит много записей, может потребоваться предоставить пользователям возможность поиска определенной записи. Вместо того, чтобы искать данные в самом элементе управления, можно реализовать поиск, запрашивая базовый <xref:System.Windows.Forms.BindingSource>. Если элемент найден, можно использовать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> свойство, чтобы выбрать элемент и его прокрутку и отобразить.  
  
### <a name="to-implement-search"></a>В реализации поиска  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TextBox> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
2.  В окне "Свойства" измените значение свойства **Имя** на **SearchTextBox**.  
  
3.  Перетащите элемент управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
4.  В окне "Свойства" измените значение свойства **Имя** на **SearchButton**. Задайте для свойства **Текст** значение **Поиск**.  
  
5.  Дважды щелкните элемент управления <xref:System.Windows.Forms.Button> , чтобы открыть редактор кода, и добавьте следующий код в обработчик событий `SearchButton_Click` :  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     Замените *ProductsBindingSource* с именем <xref:System.Windows.Forms.BindingSource> для вашей <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>и замените *ProductID* с именем поля, которое требуется выполнить поиск.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
