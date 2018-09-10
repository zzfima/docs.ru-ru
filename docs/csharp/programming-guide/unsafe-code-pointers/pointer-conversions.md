---
title: Преобразования указателей (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: db809fa9e086351184adcac43d67f53e9456894c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43777401"
---
# <a name="pointer-conversions-c-programming-guide"></a>Преобразования указателей (Руководство по программированию на C#)
В следующей таблице приведены предопределенные неявные преобразования указателей. Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.  
  
## <a name="implicit-pointer-conversions"></a>Неявные преобразования указателей  
  
|Исходный тип|Кому|  
|----------|--------|  
|Любой тип указателя|void*|  
|null|Любой тип указателя|  
  
 Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения. Эти преобразования показаны в следующей таблице.  
  
## <a name="explicit-pointer-conversions"></a>Явные преобразования указателей  
  
|Исходный тип|Кому|  
|----------|--------|  
|Любой тип указателя|Любой другой тип указателя|  
|sbyte, byte, short, ushort, int, uint, long или ulong|Любой тип указателя|  
|Любой тип указателя|sbyte, byte, short, ushort, int, uint, long или ulong|  
  
## <a name="example"></a>Пример  
 В следующем примере указатель на `int` преобразуется в указатель на `byte`. Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной. При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [Типы](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
