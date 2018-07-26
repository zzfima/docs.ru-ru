---
title: 'Практическое: создать форму «основной-подробности» с помощью двух элементов управления DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245545"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater (Visual Studio)
Можно отобразить связанные данные с помощью двух или более <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элементы управления для создания формы «основной/подробности». Например, может потребоваться отобразить список клиентов в одном <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, когда пользователь выбирает клиента, отображается список заказов этого клиента в секунду <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 Можно отобразить связанные данные, перетащив подчиненные элементы, которые совместно используют один и тот же узел главную таблицу из **источников данных** окна на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. К примеру, если у вас есть источник данных, который имеет таблицу Customers и связанную таблицу Orders, обе таблицы будут отображаться как узлы высшего уровня в представлении в виде дерева в **источников данных** окна. Разверните узел Customers, таким образом, чтобы просмотреть столбцы. Обратите внимание, что последний столбец в списке разворачиваемый узел, представляющий таблицу Orders. Этот узел представляет связанные заказы для клиента.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Для отображения связанных данных в двух элементов управления DataRepeater  
  
1.  Перетащите два <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управляет из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры изменения размера и положения, чтобы элементы управления их размера и положения side-by-side.  
  
3.  В меню **Данные** выберите команду **Показать источники данных**.  
  
    > [!NOTE]
    >  Если **источников данных** окно пуст, добавьте в источник данных. Дополнительные сведения см. в разделе [Добавление новых источников данных](/visualstudio/data-tools/add-new-data-sources).  
  
4.  В **источников данных** окно, выберите узел верхнего уровня в главной таблице.  
  
5.  Измените тип удаления главной таблицы на сведения, нажав кнопку **сведения** в раскрывающемся списке в узле таблицы.  
  
6.  Перетащите узел главной таблицы в области шаблона элемента первого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
7.  Разверните узел главной таблицы и выберите узел сведений для связанной таблицы.  
  
8.  Измените тип удаления таблицы сведений на сведения, нажав кнопку **сведения** в раскрывающемся списке в узле таблицы.  
  
9. Выберите этот узел таблицы и перетащите его в область шаблона элемента второго <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Отображение связанных данные в приложении Windows Forms](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
