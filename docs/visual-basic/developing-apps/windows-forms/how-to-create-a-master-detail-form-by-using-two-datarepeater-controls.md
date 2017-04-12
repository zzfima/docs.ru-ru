---
title: "Практическое руководство: создание главные и подчиненные формы с помощью двух элементов управления DataRepeater (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 23789bb11cab17b50928651e1dc00d5d59640c0f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater (Visual Studio)
Можно отобразить связанные данные с помощью двух или более <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>элементы управления для создания главного и подчиненного.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Например, может потребоваться отобразить список клиентов в одном <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, когда пользователь выбирает клиента, отображается список заказов этого клиента в секунду <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 Можно отобразить связанные данные, перетащив подчиненные элементы, которые совместно используют один и тот же узел главной таблицы из **источников данных** окна на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Например, если имеется источник данных, который имеет таблицу Customers и связанную таблицу Orders, обе таблицы будут отображаться как узлы верхнего уровня в представлении дерева в **источников данных** окна. Разверните узел Customers, чтобы просмотреть столбцы. Обратите внимание, что последний столбец в списке является разворачиваемым узлом, который представляет таблицу Orders. Этот узел представляет связанные заказы для клиента.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Для отображения связанных данных в двух элементах управления DataRepeater  
  
1.  Перетащите два <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управляет из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Перетащите маркеры изменения размера и положения элементов управления их размера и положения side-by-side.  
  
3.  В меню **Данные** выберите команду **Показать источники данных**.  
  
    > [!NOTE]
    >  Если **источников данных** окно пусто, добавьте в источник данных. Дополнительные сведения см. в разделе [добавить новые источники данных](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).  
  
4.  В **источников данных** окно, выберите узел верхнего уровня в главной таблице.  
  
5.  Измените тип переноса главной таблицы на сведения, выбрав **сведений** в раскрывающемся списке узла таблицы.  
  
6.  Перетащите узел главной таблицы в область шаблона элемента первого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
7.  Разверните узел главной таблицы и выберите дочерний узел для связанной таблицы.  
  
8.  Измените тип переноса дочерней таблицы на сведения, выбрав **сведений** в раскрывающемся списке узла таблицы.  
  
9. Выберите этот узел таблицы и перетащите его в область шаблона элемента второго <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Практическое руководство: отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: отображение связанных данных в приложении Windows Forms приложения](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)   
 [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
