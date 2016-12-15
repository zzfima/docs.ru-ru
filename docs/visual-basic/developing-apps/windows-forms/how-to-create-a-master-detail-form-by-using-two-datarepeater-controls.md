---
title: "Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, таблицы типа "основная-подробности""
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно отобразить связанные данные при помощи двух или более элементов управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> для создания главного и подчиненного представлений.  Например, может быть необходимо отобразить список клиентов в одном элементе управления<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, и тогда пользователь выбирает клиента, и отображает список его заказов во втором элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 Можно отобразить связанные данные, перетащив подчиненные элементы, которые используют тот же самый главный узел таблицы, из окна **Источники данных** в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Например, если имеется источник данных, который имеет таблицу Customers и связанную таблицу Orders, обе таблицы будут отображаться как узлы верхнего уровня \(в иерархическом представлении\) в окне **Источники данных**.  Разверните узел Customers, чтобы видеть столбцы.  Заметьте, что последний столбец в списке является разворачиваемым узлом, который представляет таблицу Orders.  Этот узел представляет заказы, связанные с клиентом.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Чтобы отобразить связанные данные в двух элементах управления DataRepeater  
  
1.  Перетащите два элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> из вкладки **Visual Basic PowerPacks** в **панели элементов** на форму или контейнерный элемент управления.  
  
2.  Измените размер и расположение в соответствии с размером и расположением элементов управления, расположенных бок о бок.  
  
3.  В меню **Данные** выберите пункт **Показать источники данных**.  
  
    > [!NOTE]
    >  Если окно **Источники данных** пусто, то добавьте в него источник данных.  Дополнительные сведения см. в разделе [Общие сведения об источниках данных](/visual-studio/data-tools/add-new-data-sources).  
  
4.  В окне **Источники данных**, выберите узел верхнего уровня в главной таблице.  
  
5.  Измените тип переноса главной таблицы на Сведения, выбрав **Сведения** из раскрывающегося списка узла таблицы.  
  
6.  Перетащите узел главной таблицы в область шаблона элемента первого элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
7.  Разверните узел главной таблицы и выберите дочерний узел для связанной таблицы.  
  
8.  Измените тип переноса дочерней таблицы на Сведения, выбрав **Сведения** из раскрывающегося списка узла таблицы.  
  
9. Выберите этот узел таблицы и перетащите его в область шаблона элемента второго элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Отображение связанных данные в приложении Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)