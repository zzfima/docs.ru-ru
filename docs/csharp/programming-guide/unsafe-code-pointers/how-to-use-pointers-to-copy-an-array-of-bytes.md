---
title: Как выполнить Руководство по программированию на C#. Использование указателей для копирования массива байтов
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 49151c6d2a573a24e63f733a5279faeee40de1b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241130"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Использование указателей для копирования массива байтов

В следующем примере указатели используются для копирования байт из одного массива в другой.

В этом примере применяется ключевое слово [unsafe](../../language-reference/keywords/unsafe.md), которое позволяет использовать указатели в методе `Copy`. Оператор [fixed](../../language-reference/keywords/fixed-statement.md) используется для объявления указателей исходного и конечного массивов. Оператор `fixed` *закрепляет* расположение исходного и конечного массивов в памяти, чтобы они не перемещались при сборке мусора. Закрепление этих блоков памяти отменяется, когда завершается обработка блока `fixed`. Поскольку метод `Copy` в этом примере использует ключевое слово `unsafe`, он должен быть скомпилирован с параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).

В этом примере доступ к элементам обоих массивов выполняется с помощью индексов, а не второго неуправляемого указателя. Объявление указателей `pSource` и `pTarget` закрепляет массивы. Эта возможность доступна начиная с C# 7.3.

## <a name="example"></a>Пример

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)  
- [Небезопасный код и указатели](index.md)  
- [-unsafe (параметры компилятора C#)](../../language-reference/compiler-options/unsafe-compiler-option.md)  
- [Сборка мусора](../../../standard/garbage-collection/index.md)  
