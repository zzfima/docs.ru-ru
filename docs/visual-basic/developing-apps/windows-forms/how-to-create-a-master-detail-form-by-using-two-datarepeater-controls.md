---
title: 'Как: создать подробный форму с помощью двух элементов управления DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f17cb86c3ea0ea056291a51becd7ecf9f73d0a73
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater (Visual Studio)
Можно отобразить связанные данные с помощью двух или более <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элементы управления для создания главного и подчиненного. Например, может потребоваться отобразить список клиентов в одном <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, когда пользователь выбирает клиента, отображается список заказов этого клиента в секунду <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 Можно отобразить связанные данные, перетащив подчиненные элементы, которые совместно используют один и тот же узел главной таблицы из **источники данных** окна на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Например, если имеется источник данных, который имеет таблицу Customers и связанную таблицу Orders, обе таблицы будут отображаться как узлы верхнего уровня в представлении дерева в **источники данных** окна. Разверните узел Customers, чтобы просмотреть столбцы. Обратите внимание, что последний столбец в списке является расширяемым узлом, который представляет таблицу Orders. Этот узел представляет связанные заказы для клиента.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Для отображения связанных данных в двух элементах управления DataRepeater  
  
1.  Перетащите два <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управляет из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры изменения размера и положения, чтобы размер элементов управления и располагать их рядом друг с другом.  
  
3.  В меню **Данные** выберите команду **Показать источники данных**.  
  
    > [!NOTE]
    >  Если **источники данных** окно пусто, добавьте в источник данных. Дополнительные сведения см. в разделе [Добавление новых источников данных](/visualstudio/data-tools/add-new-data-sources).  
  
4.  В **источники данных** окно, выберите узел верхнего уровня в главной таблице.  
  
5.  Измените тип переноса главной таблицы на сведения, выбрав **сведений** в раскрывающемся списке в узле таблицы.  
  
6.  Перетащите узел главной таблицы в область шаблона первого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
7.  Разверните узел главной таблицы и выберите дочерний узел для связанной таблицы.  
  
8.  Измените тип переноса дочерней таблицы на сведения, выбрав **сведений** в раскрывающемся списке в узле таблицы.  
  
9. Выберите этот узел таблицы и перетащите его в область шаблона элемента второго <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Отображение связанных данные в приложении Windows Forms](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
