---
title: Руководство по программированию на C#. Преобразования указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 81b2110e6a571e174693fd272d1c6b4bf44dbae3
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588215"
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
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Типы указателей](./pointer-types.md)
- [Типы](../../language-reference/keywords/types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
- [Оператор fixed](../../language-reference/keywords/fixed-statement.md)
- [stackalloc](../../language-reference/operators/stackalloc.md)
