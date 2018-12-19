---
title: Справочник по C#. Оператор return
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 058dc1d51099196559bee4ec2b96dc883e813f93
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236563"
---
# <a name="return-c-reference"></a>return (Справочник по C#)

Оператор `return` завершает выполнение метода, в котором он присутствует, и возвращает управление вызывавшему методу. Он также возвращает необязательное значение. Если метод имеет тип `void`, оператор `return` можно опустить.

 Если оператор return находится внутри блока `try`, блок `finally`, если он существует, будет выполняться до возврата управления вызывающему методу.

## <a name="example"></a>Пример

 В приведенном ниже примере метод `CalculateArea()` возвращает локальную переменную `area` в виде значения [double](double.md).

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Оператор return](/cpp/cpp/return-statement-cpp)
- [Операторы перехода](jump-statements.md)
