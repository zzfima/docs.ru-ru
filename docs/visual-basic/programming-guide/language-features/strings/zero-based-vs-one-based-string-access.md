---
title: "Отсчитываемый от нуля vs. Строка с индексацией доступ в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Отсчитываемый от нуля vs. Строка с индексацией доступ в Visual Basic
В этом разделе сравнивается как [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют доступ к символам в строке. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Всегда предоставляет отсчитываемый от нуля доступ к символам в строке, в то время как [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.  
  
## <a name="one-based"></a>Единицы  
 Пример с единицы [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] функция, рассмотрите возможность `Mid` функции. Он принимает аргумент, указывающий положение символа, с которой начинается подстрока, начиная с позиции 1. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Принимает индекс символа в строке является подстрока для запуска, начиная с позиции 0. Таким образом, если имеется строка «ABCDE» отдельные символы нумеруются 1,2,3,4,5 для использования с `Mid` функцию, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> метод.  
  
## <a name="zero-based"></a>Отсчитываемый от нуля  
 Например, начинающийся с нуля [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] функция, рассмотрите возможность `Split` функции. Он разбивает строку и возвращает массив, содержащий подстроки. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Метод также разбивает строку и возвращает массив, содержащий подстроки. Поскольку `Split` функции и <xref:System.String.Split%2A> возвращении метода [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] массивы, они должны быть отсчитываемый от нуля.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
