---
title: Создание простой параллельной программы с использованием Parallel.ForEach
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 02b94b673dc4468e68a1dadd83aab0e3bfcfaa16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160304"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Практическое руководство. написание простого цикла Parallel.ForEach

В этом примере показано, как использовать цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> для включения параллелизма данных в любом источнике данных <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.

> [!NOTE]
> В этой документации для определения делегатов в PLINQ используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Пример

В этом примере предполагается, что у вас есть несколько JPG-файлов в папке *C:\Пользователи\Общие\Изображения\Образцы изображений* и что будет создана новая вложенная папка *Измененные*. При выполнении примера каждое изображение JPG в папке *Образцы изображений* будет повернуто и сохранено в папку *Измененные*. Эти два пути при необходимости можно изменить.

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

Цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> действует как цикл <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>. Цикл разделяет исходную коллекцию на секции и распределяет задачи по нескольким потокам с учетом доступной среды системы. Чем больше в системе процессоров, тем быстрее выполняются параллельные методы. Для некоторых исходных коллекций, в зависимости от размера источника и типа выполняемых работ, последовательный цикл может оказаться быстрее. Дополнительные сведения о производительности см. в статье [Потенциальные ошибки, связанные с параллелизмом данных и задач](potential-pitfalls-in-data-and-task-parallelism.md).

Дополнительные сведения о параллельных циклах см. в статье [Практическое руководство. Написание простого цикла Parallel.For](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).

Чтобы применить <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> для неуниверсальной коллекции, вы можете преобразовать ее в универсальную коллекцию с помощью метода расширения <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType>, как показано в следующем примере.

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

Также вы можете использовать Parallel LINQ (PLINQ) для параллельной обработки источников данных <xref:System.Collections.Generic.IEnumerable%601>. PLINQ позволяет применять декларативный синтаксис запроса для описания поведения цикла. Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).

## <a name="compile-and-run-the-code"></a>Скомпилируйте и запустите код.

Код можно скомпилировать как консольное приложение для .NET Framework или .NET Core.

В Visual Studio существуют шаблоны консольных приложений Visual Basic и C# для Windows Desktop и .NET Core.

В командной строке можно использовать команды .NET Core CLI (например, `dotnet new console` или `dotnet new console -lang vb`). Также вы можете создать файл и использовать компилятор командной строки для приложения .NET Framework.

Для проекта .NET Core необходимо сослаться на пакет NuGet **System.Drawing.Common**. В Visual Studio используйте диспетчер пакетов NuGet для установки пакета. Кроме того, вы можете добавить ссылку на пакет в файл \*.csproj или \*.vbproj:

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

Чтобы запустить консольное приложение .NET Core из командной строки, используйте `dotnet run` в папке, которая содержит ваше приложение.

Чтобы запустить консольное приложение из Visual Studio, нажмите клавишу **F5**.

## <a name="see-also"></a>См. также

- [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
