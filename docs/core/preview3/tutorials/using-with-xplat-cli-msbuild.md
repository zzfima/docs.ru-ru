---
title: "Начало работы с .NET Core в Windows, Linux или Mac OS с помощью командной строки (версия-кандидат 4 средств .NET Core) | Документы Майкрософт"
description: "Начало работы с .NET Core в Windows, Linux или Mac OS с помощью интерфейса командной строки (CLI) .NET Core"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 41632e63-d5c6-4427-a09e-51dc1116d45f
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 4c17da61f492e17edf4d69d79be430ead3dd0cc6

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line-net-core-tools-rc4"></a>Начало работы с .NET Core в Windows, Linux или Mac OS с помощью командной строки (версия-кандидат 4 средств .NET Core)

> [!WARNING]
> Эта статья применима к версии-кандидату 4 средств .NET Core. Версия этой статьи об инструментах .NET Core (предварительная версия 2): [Начало работы с .NET Core в Windows, Linux и Mac OS из командной строки](../../tutorials/using-with-xplat-cli.md).

В этом руководстве показано, как с помощью средств командной строки в .NET Core создавать кроссплатформенные консольные приложения.  Мы начнем с самого простого консольного приложения, а затем охватим несколько проектов, включая тестирование. Возможности будут добавляться поэтапно на основе того, что вы уже узнали и создали.

Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../tools/dotnet.md).

## <a name="prerequisites"></a>Предварительные требования

Прежде чем начинать работу, убедитесь, что у вас есть [версия-кандидат 4 или более поздняя версия средств CLI .NET Core](https://github.com/dotnet/core/blob/master/release-notes/preview3-download.md).  Вам также потребуется текстовый редактор.

## <a name="hello-console-app"></a>Первое консольное приложение

Сначала перейдите к существующей папке или создайте папку с любым именем на свое усмотрение.  Для образца кода, который можно найти [здесь](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild), выбрано имя Hello.

Откройте окно командной строки и введите следующее:

```
$ dotnet new
$ dotnet restore
$ dotnet run
```

Вкратце рассмотрим эти команды.

1. `$ dotnet new`

   [`dotnet new`](../tools/dotnet-new.md) создает актуальный файл проекта `Hello.csproj` с зависимостями, необходимыми для создания консольного приложения.  Эта команда также создает `Program.cs` — простой файл, содержащий точку входа для приложения.
   
   `Hello.csproj`:
   ```xml
    <Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
        <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
        
        <PropertyGroup>
            <OutputType>Exe</OutputType>
            <TargetFramework>netcoreapp1.0</TargetFramework>
        </PropertyGroup>

        <ItemGroup>
            <Compile Include="**\*.cs" />
            <EmbeddedResource Include="**\*.resx" />
        </ItemGroup>

        <ItemGroup>
            <PackageReference Include="Microsoft.NETCore.App">
                <Version>1.0.1</Version>
            </PackageReference>
            <PackageReference Include="Microsoft.NET.Sdk">
                <Version>1.0.0-alpha-20161104-2</Version>
                <PrivateAssets>All</PrivateAssets>
            </PackageReference>
        </ItemGroup>
        
        <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
   ```

   В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.

   * Тег `Import` добавляет определенные свойства, которые являются общими для всех проектов .NET Core.
   * Тег `OutputType` указывает, что мы создаем исполняемый файл — другими словами, консольное приложение.
   * Тег `TargetFramework` указывает, какая среда выполнения .NET является нашей целью. В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку во всех средах за одну операцию. В этом руководстве рассматривается сборка только для платформы .NET Core 1.0.
   * Тег `Compile` указывает компилятору собирать все файлы в текущем каталоге и всех его подкаталогах, имеющих расширение файла `.cs`, — другими словами, все файлы C# в проекте. В расширенных сценариях можно исключать файлы, но в этом руководстве и в большинстве простых сценариев эту строку можно оставить без изменений.
   * Тег `EmbeddedResource` предписывает системе сборки внедрить файлы локализации с расширением `.resx` в скомпилированный исполняемый файл. Мы не будем использовать эту функцию в данном руководстве.
   * Теги `PackageReference` определяют, какие пакеты зависимостей следует восстановить и включить при сборке приложения. В ссылке на каждый пакет указано имя пакета в атрибуте `Include` и номер версии. В наиболее расширенных сценариях вам предстоит добавлять дополнительные ссылки на пакеты. Можно также ссылаться на другие проекты на диске.

   `Program.cs`:
   ```csharp
   using System;

   namespace ConsoleApplication
   {
       public class Program
       {
           public static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   Программа начинается с команды `using System`, что означает "добавить все данные пространства имен `System` в область видимости для этого файла". Пространство имен `System` содержит основные конструкции, такие как `string`, или числовые типы.

   Затем мы определим пространство имен с именем ConsoleApplication. Вы можете сменить это имя на любое другое. Класс Program определяется в этом пространстве имен с использованием метода `Main`, который принимает массив строк в качестве аргумента. Этот массив будет содержать список передаваемых аргументов, когда будет вызвана скомпилированная программа. В такой форме программа не использует этот массив. Единственное ее действие — вывод надписи "Hello World!" "Hello World!". Мы можем добавить разнообразия, заменив `Console.WriteLine` следующим кодом.

   ```csharp
   if (args.Length > 0)
   {
       Console.WriteLine($"Hello {args[0]}!");
   }
   else
   {
       Console.WriteLine("Hello World!");
   }
   ```

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md) вызывает [NuGet](http://nuget.org) (диспетчер пакетов .NET) для восстановления дерева зависимостей. NuGet анализирует файл `Hello.csproj`, скачивает указанные в нем зависимости (или извлекает их из кэша на вашем компьютере) и записывает файл `obj/project.assets.json`.  Файл `project.assets.json` необходим для компиляции и запуска.
   
   Файл `project.assets.json` содержит сохраняемую полную схему зависимостей NuGet и другие сведения, описывающие приложение.  Этот файл считывается другими средствами, такими как `dotnet build` и `dotnet run`, что позволяет им обрабатывать исходный код с правильным набором зависимостей NuGet и разрешений привязки.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) вызывает `dotnet build` для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.
   
    ```
    $ dotnet run
    Hello World!
    ```

    Кроме того, вы можете выполнить [`dotnet build`](../tools/dotnet-build.md), чтобы скомпилировать код, не запуская консольные приложения сборки. В результате мы получаем скомпилированное приложение `bin/Debug/netcoreapp1.0/Hello.dll`, которое можно выполнить при помощи `dotnet bin\Debug\netcoreapp1.0\Hello.dll` в Windows и `dotnet bin/Debug/netcoreapp1.0/Hello.dll` других операционных системах. Можно указать дополнительный параметр в командной строке (если используется ОС Windows):

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll .NET
    Hello .NET!
    ```

    В расширенном сценарии можно собрать приложение в качестве автономного набора файлов для определенной платформы, которые можно развернуть и запустить на компьютере без .NET Core. Чтобы получить подробные сведения, см. статью [.NET Core Application Deployment](../deploying/index.md) (Развертывание приложений .NET Core).

### <a name="augmenting-the-program"></a>Расширение программы

Давайте немного изменим файл.  С числами Фибоначчи интересно работать, поэтому давайте попробуем сделать следующее:

`Program.cs`:

```csharp
using static System.Console;

namespace ConsoleApplication
{
    public class Program
    {
        public static int FibonacciNumber(int n)
        {
            int a = 0;
            int b = 1;
            int tmp;
            
            for (int i = 0; i < n; i++)
            {
                tmp = a;
                a = b;
                b += tmp;
            }
            
            return a;   
        }
        
        public static void Main(string[] args)
        {
            WriteLine("Hello World!");
            WriteLine("Fibonacci Numbers 1-15:");
            
            for (int i = 0; i < 15; i++)
            {
                WriteLine($"{i+1}: {FibonacciNumber(i)}");
            }
        }
    }
}
```

Затем запустим программу (необходимо использовать компьютер с Windows и изменить имя каталога проекта на Fibonacci):

```
$ dotnet build
$ dotnet bin\Debug\netcoreapp1.0\win10-x64\Fibonacci.exe
1: 0
2: 1
3: 1
4: 2
5: 3
6: 5
7: 8
8: 13
9: 21
10: 34
11: 55
12: 89
13: 144
14: 233
15: 377
```

Вот и все!  Вы можете расширять файл `Program.cs` по своему усмотрению.

## <a name="adding-some-new-files"></a>Добавление новых файлов

Программы на основе одного файла подходят для решения простых одиночных задач, однако, если вы создаете программу, состоящую из нескольких компонентов, скорее всего, вам потребуется разделить ее на несколько файлов.  Это упростит работу.

Создайте файл и назначьте ему уникальное пространство имен:

```csharp
using System;

namespace NumberFun
{
    // code can go here
} 
```

Далее включите его в файл `Program.cs`:

```csharp
using NumberFun;
```

Наконец, можно выполнить сборку:

`$ dotnet build`

После этого наступает самое интересное — реализация задач, выполняемых файлом.

### <a name="example-a-fibonacci-sequence-generator"></a>Пример. Генератор последовательностей Фибоначчи

Предположим, что вы хотите использовать в качестве основы предыдущий пример, реализовав в нем кэширование значений Фибоначчи и рекурсию.  Код для [лучшего примера чисел Фибоначчи](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/FibonacciBetterMsBuild) может использовать новый файл `FibonacciGenerator.cs` со следующим кодом.

```csharp
using System;
using System.Collections.Generic;

namespace NumberFun
{
    public class FibonacciGenerator
    {
        private Dictionary<int, int> _cache = new Dictionary<int, int>();
        
        private int Fib(int n) => n < 2 ? n : FibValue(n - 1) + FibValue(n - 2);
        
        private int FibValue(int n)
        {
            if (!_cache.ContainsKey(n))
            {
                _cache.Add(n, Fib(n));
            }
            
            return _cache[n];
        }
        
        public IEnumerable<int> Generate(int n)
        {
            for (int i = 0; i < n; i++)
            {
                yield return FibValue(i);
            }
        }
    }
}
```

Теперь измените метод `Main()` в файле `Program.cs`, как показано ниже.

```csharp
using System;
using NumberFun;

class Program
{
    static void Main(string[] args)
    {
        var generator = new FibonacciGenerator();
        foreach (var digit in generator.Generate(15))
        {
            Console.WriteLine(digit);
        }
    }
}
```

Наконец, запустите программу.

```
$ dotnet run
0
1
1
2
3
5
8
13
21
34
55
89
144
233
377
```

Вот и все!

## <a name="conclusion"></a>Заключение
 
Надеемся, это руководство помогло вам понять, как создавать консольные приложения .NET разного уровня сложности: от самых простых до многопроектных систем с модульными тестами.  Ваш следующий шаг — создание собственного консольного приложения.
 
Если вас интересует более сложный пример консольного приложения, просмотрите руководство [Организация и тестирование проектов с помощью командной строки .NET Core (версия-кандидат 4 средств .NET Core)](using-with-xplat-cli-msbuild-folders.md).



<!--HONumber=Feb17_HO2-->


