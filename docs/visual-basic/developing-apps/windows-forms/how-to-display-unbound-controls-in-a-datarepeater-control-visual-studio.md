---
title: "Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "DataRepeater"
  - "DataRepeater, добавление несвязанных элементов управления"
  - "отображение несвязанных данных"
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В дополнение к связанным элементам управления в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> можно добавить другие элементы управления, такие как статическая метка или изображение, повторяющееся на каждом элементе в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
> [!NOTE]
>  Необходимо также иметь как минимум один связанный с элементом управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемент, или во время выполнения ничего не будет отображаться.  
  
### Чтобы добавить несвязанные элементы управления в DataRepeater  
  
1.  Перетащите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> из вкладки **Visual Basic PowerPacks** в **панели элементов** на форму или контейнерный элемент управления.  
  
2.  Измените размер и расположение в соответствии с размером и расположением элемента управления.  
  
     Можно также изменить размер или переместить управляющий элемент, изменив свойства **Размер** и **Положение** в окне "Свойства".  
  
3.  Добавьте как минимум один связанный с данными элемент управления в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Дополнительные сведения см. в разделе [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Перетащите элемент управления из **панели элементов** в область шаблона элемента для элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
     Обратите внимание, что у элемента управления две прямоугольных области.  Внутренняя область — *шаблон элемента*; элементы управления, добавленные в шаблон, будут повторены в каждом элементе элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> во время выполнения.  Внешняя область является *окном просмотра*, в котором будут отображены элементы; элементы управления, добавленные в эту область, не будут отображены во время выполнения.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)