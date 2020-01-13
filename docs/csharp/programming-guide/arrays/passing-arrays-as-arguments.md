---
title: Руководство по программированию на C#. Передача массивов в качестве аргументов
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 2e53008910a9062ada25680eb4b8e54a225fd226
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705695"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>Передача массивов в качестве аргументов (руководство по программированию на C#)

Массивы можно передавать в качестве аргументов в параметры метода. Поскольку массивы представляют собой ссылочные типы, метод может изменять значения элементов.

## <a name="passing-single-dimensional-arrays-as-arguments"></a>Передача одномерных массивов в качестве аргументов

Инициализированный одномерный массив можно передать в метод. Например, следующий оператор передает массив в метод печати.

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

В следующем примере кода показана разделяемая реализация метода печати.

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a>Пример

В следующем примере массив строк инициализируется и передается в качестве аргумента в метод `DisplayArray` для строк. Этот метод отображает элементы массива. Затем метод `ChangeArray` размещает элементы массива в обратном порядке, а метод `ChangeArrayElements` изменяет первые три элемента массива. После возврата каждого метода метод `DisplayArray` показывает, что передача массива по значению не препятствует изменению элементов массива.

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a>Передача многомерных массивов в качестве аргументов

Инициализированный многомерный массив можно передать в метод так же, как и одномерный массив.

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

В следующем коде показано разделяемое объявление метода печати, который принимает в качестве аргумента двухмерный массив.

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

Новый массив можно инициализировать и передать за один шаг, как показано в следующем примере.

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a>Пример

В следующем примере инициализируется двухмерный массив целых чисел, который передается в метод `Print2DArray`. Этот метод отображает элементы массива.

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Массивы](index.md)
- [Одномерные массивы](single-dimensional-arrays.md)
- [Многомерные массивы](multidimensional-arrays.md)
- [Массивы массивов](jagged-arrays.md)
