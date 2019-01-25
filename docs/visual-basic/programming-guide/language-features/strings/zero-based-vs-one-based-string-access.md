---
title: Отсчитываемый от нуля vs. Доступ от единицы строки в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: d4b2f73f8955b103e70e240e714e2b31d6198438
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535543"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Отсчитываемый от нуля vs. Доступ от единицы строки в Visual Basic
В этом разделе сравнивается как Visual Basic и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют доступ к символам в строке. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Всегда обеспечивает (с нуля) доступ к символам в строке, тогда как Visual Basic предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.  
  
## <a name="one-based"></a>От единицы  
 Пример функции Visual Basic от единицы, рассмотрите возможность `Mid` функции. Он принимает аргумент, указывающий позицию символа, с которой начинается подстрока, начиная с позиции 1. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Принимает индекс символа в строке, по которому подстроки является запуск, начиная с позиции 0. Таким образом, если имеется строка «ABCDE» отдельных символов, нумеруются 1,2,3,4,5 для использования с `Mid` функция, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> метод.  
  
## <a name="zero-based"></a>Отсчитываемый от нуля  
 Пример функции Visual Basic (с нуля), рассмотрите возможность `Split` функции. Она разбивает строку и возвращает массив, содержащий подстроки. [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Метод также разбивает строку и возвращает массив, содержащий подстроки. Так как `Split` функции и <xref:System.String.Split%2A> метод возвращает [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] массивы, они должны быть отсчитываемый от нуля.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
