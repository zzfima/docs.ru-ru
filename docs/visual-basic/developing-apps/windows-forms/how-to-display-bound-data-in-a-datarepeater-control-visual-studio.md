---
title: "Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, привязка данных"
  - "DataRepeater, отображение элементов управления с привязкой"
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Наиболее общее использование элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> — отображение связанных данных из базы данных или других источников данных.  
  
 В дополнение к связанным элементам управления можно добавить другие элементы управления, такие как статическая метка или изображение, повторяющееся на каждом элементе в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Дополнительные сведения см. в разделе [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 Также можно выполнить привязку к источнику данных во время выполнения, задав свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> значение `True` и указав источник данных в качестве значения свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>.  В этом случае необходимо управлять всеми аспектами взаимодействия с источником данных.  Дополнительные сведения см. в разделе [Виртуальные режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Чтобы создать управляющий элемент DataRepeater с привязкой к данным  
  
1.  Перетащите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> из вкладки **Visual Basic PowerPacks** в **панели элементов** на форму или контейнерный элемент управления.  
  
2.  Измените размер и расположение в соответствии с размером и расположением элемента управления.  
  
     Обратите внимание, что у элемента управления две прямоугольных области.  Верхняя область — *шаблон элемента*; элементы управления, добавленные в шаблон, будут повторены в каждом элементе элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> во время выполнения.  Нижняя область является *окном просмотра*, в котором будут отображены элементы.  
  
     Можно также изменить размер или переместить управляющий элемент или шаблон элемента, изменив свойства **Размер** и **Положение** в окне "Свойства".  
  
3.  В меню **Данные** выберите пункт **Показать источники данных**.  
  
    > [!NOTE]
    >  Если окно **Источники данных** пусто, то добавьте в него источник данных.  Дополнительные сведения см. в разделе [Общие сведения об источниках данных](/visual-studio/data-tools/add-new-data-sources).  
  
4.  В окне **Источники данных**, выберите узел верхнего уровня для таблицы, содержащей данные, которые необходимо связать.  
  
5.  Измените тип переноса таблицы на `Details`, нажав `Details` в раскрывающемся списке узла таблицы.  
  
6.  Выберите узел таблицы и перетащите его в область шаблона элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
     Можно определить, какие типы элементов управления будут отображаться для каждого поля.  Дополнительные сведения см. в разделе [Задание поведения, при котором элемент управления создается при перетаскивании из окна "Источники данных"](/visual-studio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)