---
title: Лямбда-выражения в PLINQ и библиотеке параллельных задач
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: d1b716e977702d03db176da70be00a1e5c789a4b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129032"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a>Лямбда-выражения в PLINQ и библиотеке параллельных задач

Библиотека параллельных задач (TPL) содержит множество методов, которые принимают в качестве входных параметров один из делегатов семейства <xref:System.Func%601?displayProperty=nameWithType> или <xref:System.Action?displayProperty=nameWithType>. Используйте эти делегаты для передачи пользовательской программной логики в параллельный цикл, задачу или запрос. В примерах кода для библиотеки параллельных задач и PLINQ лямбда-выражения используются для создания экземпляров этих делегатов как встроенных блоков кода. В этом разделе дается краткое введение в делегаты Func и Action и демонстрируется использование лямбда-выражений в библиотеке параллельных задач и PLINQ.

> [!NOTE]
> Дополнительные сведения о делегатах см. в разделах [Делегаты](../../csharp/programming-guide/delegates/index.md) и [Делегаты](../../visual-basic/programming-guide/language-features/delegates/index.md). Дополнительные сведения о лямбда-выражениях в C# и Visual Basic см. в разделах [Лямбда-выражения](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) и [Лямбда-выражения](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="func-delegate"></a>Делегат Func

Делегат `Func` инкапсулирует метод, который возвращает значение. В сигнатуре Func последний или крайний правый тип параметра всегда указывает возвращаемый тип. Распространенной причиной ошибок компилятора является попытка передать в <xref:System.Func%602?displayProperty=nameWithType> два входных параметра. На самом деле этот тип принимает только один входной параметр. Библиотека классов Framework определяет 17 версий для `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType> и так далее вплоть до <xref:System.Func%6017?displayProperty=nameWithType>.

## <a name="action-delegate"></a>Делегат Action

Делегат <xref:System.Action?displayProperty=nameWithType> инкапсулирует метод (Sub в Visual Basic), который не возвращает значение или возвращает [void](../../csharp/language-reference/keywords/void.md). В сигнатуре типа Action параметры типа представляют только входные параметры. Как и в случае с делегатом Func, библиотека классов Framework определяет 17 версий делегата Action, начиная с версии без параметров типа и заканчивая версией с 16 параметрами типа.

## <a name="example"></a>Пример

Следующий пример демонстрирует метод <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> позволяющий выразить делегаты Func и Action через лямбда-выражения.

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a>См. также

- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
