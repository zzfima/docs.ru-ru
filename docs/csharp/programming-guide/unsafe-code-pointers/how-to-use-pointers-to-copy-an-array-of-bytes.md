---
title: "Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
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
ms.openlocfilehash: 808a74f75e4dcbcec47735d98063138e2c7456e5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)
В следующем примере указатели используются для копирования байт из одного массива в другой.  
  
 В этом примере применяется ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md), которое позволяет использовать указатели в методе `Copy`. Оператор [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) используется для объявления указателей исходного и конечного массивов. Это *закрепляет* расположение исходного и конечного массивов в памяти, чтобы они не перемещались при сборке мусора. Закрепление этих блоков памяти отменяется, когда завершается обработка блока `fixed`. Поскольку метод `Copy` в этом примере использует ключевое слово `unsafe`, он должен быть скомпилирован с параметром компилятора **/unsafe**. Чтобы задать параметр в Visual Studio, щелкните правой кнопкой мыши имя проекта, затем щелкните **Свойства**. На вкладке **Сборка** выберите **Разрешить небезопасный код**.  
  
## <a name="example"></a>Пример  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [/unsafe (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)   
 [Сборка мусора](../../../standard/garbage-collection/index.md)

