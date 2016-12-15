---
title: "Что лучше: отсчет индексации с нуля или с единицы? (Visual Basic) | Microsoft Docs"
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
  - "строки [Visual Basic], индексация"
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Что лучше: отсчет индексации с нуля или с единицы? (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом разделе проводится сравнение того, как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] и [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] предоставляют доступ к символам в строке.  [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] символы в строке считает с нуля, тогда как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] введет индексацию либо с нуля, либо с единицы, в зависимости от функции.  
  
## Индексация с единицы  
 Примером функции [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], ведущей отсчет с единицы, является функция `Mid`.  Она принимает аргумент, указывающий положение символа, с которого будет начинаться подстрока, начиная с позиции 1.  Метод [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName> принимает индекс символа в строке, с которого начинается подстрока, начиная с позиции 0.  Следовательно, если имеется строка "ABCDE", то отдельные символы нумеруются как 1,2,3,4,5 для использования в функции `Mid`, но как 0,1,2,3,4 для использования в методе <xref:System.String.Substring%2A?displayProperty=fullName>.  
  
## Индексация с нуля  
 Примером функции [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], ведущей отсчет с нуля, является функция `Split`.  Она разбивает строку и возвращает массив, содержащий подстроки.  В методе [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName> также разбивается строка и возвращает массив, содержащий подстроки.  Поскольку функция `Split` и метод <xref:System.String.Split%2A> возвращают массивы [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], индексация у них должна вестись от нуля.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A>   
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)