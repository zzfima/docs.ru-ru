---
title: "Отсчитываемый от нуля vs. Доступ на основе одной строки в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 6cd2cab888bf336151ed26968119431f4ffc75f4
ms.lasthandoff: 03/13/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Отсчитываемый от нуля vs. Доступ на основе одной строки в Visual Basic
В этом разделе сравнивается как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] и [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] предоставляют доступ к символам в строке. [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Всегда обеспечивает (с нуля) доступ к символам в строке, в то время как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.  
  
## <a name="one-based"></a>Единицы  
 Пример с единицы [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функция, рассмотрите возможность `Mid` функции. Он принимает аргумент, указывающий положение символа, с которой начинается подстрока, начиная с позиции 1. [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>Принимает индекс символа в строке является подстрока для запуска, начиная с позиции 0.</xref:System.String.Substring%2A?displayProperty=fullName> Таким образом, если имеется строка «ABCDE» отдельные символы нумеруются как 1,2,3,4,5 для использования с `Mid` функции, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=fullName>метод.</xref:System.String.Substring%2A?displayProperty=fullName>  
  
## <a name="zero-based"></a>Отсчитываемый от нуля  
 Пример (с нуля) [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функция, рассмотрите возможность `Split` функции. Он разбивает строку и возвращает массив, содержащий подстроки. [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>Также метод разбивает строку и возвращает массив, содержащий подстроки.</xref:System.String.Split%2A?displayProperty=fullName> Поскольку `Split` функции и <xref:System.String.Split%2A>возвращении метода [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] массивы, они должны быть от нуля.</xref:System.String.Split%2A>  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A></xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A></xref:System.String.Split%2A>   
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
