---
title: "Преобразования указателей (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a>Преобразования указателей (Руководство по программированию на C#)
В следующей таблице приведены предопределенные неявные преобразования указателей. Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.  
  
## <a name="implicit-pointer-conversions"></a>Неявные преобразования указателей  
  
|Исходный тип|Целевой тип|  
|----------|--------|  
|Любой тип указателя|void*|  
|null|Любой тип указателя|  
  
 Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения. Эти преобразования показаны в следующей таблице.  
  
## <a name="explicit-pointer-conversions"></a>Явные преобразования указателей  
  
|Исходный тип|Целевой тип|  
|----------|--------|  
|Любой тип указателя|Любой другой тип указателя|  
|sbyte, byte, short, ushort, int, uint, long или ulong|Любой тип указателя|  
|Любой тип указателя|sbyte, byte, short, ushort, int, uint, long или ulong|  
  
## <a name="example"></a>Пример  
 В следующем примере указатель на `int` преобразуется в указатель на `byte`. Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной. При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

