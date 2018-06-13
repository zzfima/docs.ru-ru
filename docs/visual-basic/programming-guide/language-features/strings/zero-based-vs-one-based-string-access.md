---
title: Отсчитываемый от нуля vs. Строка с индексацией доступ в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a0a42f72d94adf1c10865374017fa61e833df40f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649104"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Отсчитываемый от нуля vs. Строка с индексацией доступ в Visual Basic
В этом разделе сравнивается как Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют доступ к символам в строке. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Всегда обеспечивает (с нуля) доступ к символам в строке, а Visual Basic предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.  
  
## <a name="one-based"></a>Единицы  
 Пример функции Visual Basic с единицы, рассмотрите возможность `Mid` функции. Он принимает аргумент, указывающий положение символа, с которой начинается подстрока, начиная с позиции 1. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Принимает индекс символа в строке является подстрока для запуска, начиная с позиции 0. Таким образом, если имеется строка «ABCDE» отдельные символы нумеруются 1,2,3,4,5 для использования с `Mid` функцию, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> метод.  
  
## <a name="zero-based"></a>Отсчитываемый от нуля  
 Пример функции Visual Basic (с нуля), рассмотрите возможность `Split` функции. Он разбивает строку и возвращает массив, содержащий подстроки. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Метод также разбивает строку и возвращает массив, содержащий подстроки. Поскольку `Split` функции и <xref:System.String.Split%2A> возвращении метода [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] массивы, они должны быть отсчитываемый от нуля.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
