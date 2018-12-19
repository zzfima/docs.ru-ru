---
title: Справочник по C#. Параметры методов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: f6d0309a91c426123be13a4302d711c92d4ea0f7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242735"
---
# <a name="method-parameters-c-reference"></a>Параметры методов (Справочник по C#)

Параметры, объявленные для метода без [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), передаются в вызываемый метод по значению. Это значение может изменяться в методе, однако измененное значение не будет сохраняться при возврате управления вызывающей процедуре. С помощью ключевого слова параметра метода это поведение можно изменить.  
  
 В этом разделе описываются ключевые слова, которые можно использовать при объявлении параметров метода:  
  
-   [params](../../../csharp/language-reference/keywords/params.md) указывает, что этот параметр может принимать переменное количество аргументов.
  
-   [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) указывает, что этот параметр передается по ссылке, но лишь считывается вызванным методом.
  
-   [ref](../../../csharp/language-reference/keywords/ref.md) указывает, что этот параметр передается по ссылке и может быть считан или записан вызванным методом.
  
-   [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) указывает, что этот параметр передается по ссылке и записывается вызванным методом.
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)
