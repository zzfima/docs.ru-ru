---
title: Справочник по C#. Ключевое слово params
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 90d224080f607cbac96514aaf5ac6d67affef9e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713239"
---
# <a name="params-c-reference"></a>params (справочник по C#)

С помощью ключевого слова `params` можно указать [параметр метода](method-parameters.md), принимающий переменное число аргументов.

Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа. Можно также не отправлять аргументы. Если аргументы не отправляются, длина списка `params` равна нулю.

В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.

Объявленный тип параметра `params` должен быть одномерным массивом, как показано в следующем примере. В противном случае возникает ошибка компилятора [CS0225](../../misc/cs0225.md).

## <a name="example"></a>Пример

В следующем примере показаны различные способы оправки аргументов параметру `params`.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Параметры методов](method-parameters.md)
