---
title: 'Что лучше: отсчет строк с нуля или Доступ от единицы строки в Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: cc8f286de41d7e44225e889e73ff3c7b1fdbd881
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591745"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Что лучше: отсчет строк с нуля или Доступ от единицы строки в Visual Basic
В этом разделе сравниваются, как Visual Basic и .NET Framework предоставляют доступ к символам в строке. Платформа .NET Framework всегда предоставляет (с нуля) доступ к символов в строке, тогда как Visual Basic предоставляет доступ, отсчитываемый от нуля и от единицы, в зависимости от функции.  
  
## <a name="one-based"></a>От единицы  
 Пример функции Visual Basic от единицы, рассмотрите возможность `Mid` функции. Он принимает аргумент, указывающий позицию символа, с которой начинается подстрока, начиная с позиции 1. .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> принимает индекс символа в строке, по которому подстроки является запуск, начиная с позиции 0. Таким образом, если имеется строка «ABCDE» отдельных символов, нумеруются 1,2,3,4,5 для использования с `Mid` функция, но как 0,1,2,3,4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> метод.  
  
## <a name="zero-based"></a>Отсчитываемый от нуля  
 Пример функции Visual Basic (с нуля), рассмотрите возможность `Split` функции. Она разбивает строку и возвращает массив, содержащий подстроки. .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> метод также разбивает строку и возвращает массив, содержащий подстроки. Так как `Split` функции и <xref:System.String.Split%2A> метод возвращать массивы .NET Framework, они должны быть отсчитываемый от нуля.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
