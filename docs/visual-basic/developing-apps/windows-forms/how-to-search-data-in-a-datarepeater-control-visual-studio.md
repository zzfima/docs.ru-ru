---
title: "Практическое руководство. Поиск данных в элементе управления DataRepeater (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, реализация поиска"
  - "DataRepeater, поиск данных"
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Поиск данных в элементе управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При использовании элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, содержащего много записей, можно предоставить пользователям возможность поиска определенных записей.  Чтобы не искать данные в самом управляющем элементе, можно реализовать поиск, запрашивая базовый <xref:System.Windows.Forms.BindingSource>.  Если элемент найден, можно использовать свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> для выделения элемента и прокрутки до него области просмотра.  
  
### Чтобы реализовать поиск  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TextBox> из **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
2.  В окне "Свойства" измените свойство **Имя** на SearchTextBox.  
  
3.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
4.  В окне "Свойства" измените свойство **Имя** на SearchButton.  Задайте для свойства **Текст** значение "Поиск".  
  
5.  Дважды щелкните элемент управления <xref:System.Windows.Forms.Button>, чтобы открыть редактор кода, и введите следующий код в обработчик событий `SearchButton_Click`:  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-cs[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     Замените *ProductsBindingSource* именем <xref:System.Windows.Forms.BindingSource> для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> и замените *ProductID* именем поля, которое нужно найти.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)