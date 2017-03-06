---
title: "Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки"
description: "Начало работы с .NET Core в Windows, Linux или Mac OS с помощью интерфейса командной строки (CLI) .NET Core"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: be988f09-7349-43b0-97fb-3a703d4587ce
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 8f0ad79eafde695b956e89f48073dba2651b51cb

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 2). Сведения для версии-кандидата 4 средств .NET Core см. в разделе [Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки (версия-кандидат 4 средств .NET Core)](../preview3/tutorials/using-with-xplat-cli-msbuild.md).

В этом руководстве показано, как с помощью средств командной строки в .NET Core создавать базовые кроссплатформенные консольные приложения.

Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../sdk.md).

## <a name="prerequisites"></a>Предварительные требования

Перед тем как приступать, убедитесь в том, что у вас имеется [последняя версия средств CLI для .NET Core](https://www.microsoft.com/net/core). Вам также потребуется текстовый редактор.

## <a name="hello-console-app"></a>Первое консольное приложение

Перейдите к существующей папке или создайте папку с любым именем. Для образца кода, который можно найти [здесь](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/Hello), выбрано имя Hello.

Откройте окно командной строки и введите следующее:

```
$ dotnet new
$ dotnet restore
$ dotnet run
```

Вкратце рассмотрим эти команды.

1. `$ dotnet new`

   [`dotnet new`](../tools/dotnet-new.md) создает актуальный файл `project.json` с зависимостями NuGet, необходимыми для сборки консольного приложения.  Эта команда также создает `Program.cs` — простой файл, содержащий точку входа для приложения.
   
   `project.json`:
   ```json
   {
        "version": "1.0.0-*",
        "buildOptions": {
            "emitEntryPoint": true
        },
        "dependencies": {
            "Microsoft.NETCore.App": {
                "type": "platform",
                "version": "1.0.0"
            }
        },   
       "frameworks": {
            "netcoreapp1.0": {
                "imports": "dnxcore50"
            }
        }
   }
   ```
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

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md) вызывает пакет NuGet для восстановления дерева зависимостей. NuGet анализирует файл `project.json`, скачивает указанные в нем зависимости (или извлекает их из кэша на вашем компьютере) и записывает файл `project.lock.json`.  Файл `project.lock.json` необходим для компиляции и запуска.
   
   Файл `project.lock.json` содержит сохраняемую полную схему зависимостей NuGet и другие сведения, описывающие приложение.  Этот файл считывается другими средствами, такими как `dotnet build` и `dotnet run`, что позволяет им обрабатывать исходный код с правильным набором зависимостей NuGet и разрешений привязки.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) вызывает `dotnet build` для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.
   
```
$ dotnet run
Hello, World!
```

Вы также можете выполнить [`dotnet build`](../tools/dotnet-build.md), чтобы скомпилировать код, не запуская консольные приложения сборки.

### <a name="building-a-self-contained-application"></a>Сборка автономного приложения

Давайте попробуем скомпилировать автономное, а не переносимое приложение. Вы можете прочитать статью о [типах переносимости в .NET Core](../deploying/index.md), чтобы ознакомиться с различными типами приложений и способами их развертывания.

Вам необходимо внести ряд изменений в файл `project.json`, чтобы указать, что средства должны выполнить сборку автономного приложения. Эти изменения можно просмотреть в проекте [HelloNative](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloNative) в каталоге с образцами.

Первое изменение — это удаление элемента `"type": "platform"` из всех зависимостей. Единственная зависимость проекта — `"Microsoft.NETCore.App"`. Раздел `dependencies` должен выглядеть следующим образом:

```json
"dependencies": {
    "Microsoft.NETCore.App": {
        "version": "1.0.0"
    }
},
```

Далее необходимо добавить узел `runtimes`, чтобы указать все целевые среды выполнения. Например, приведенный ниже узел `runtimes` предписывает системе сборки создать исполняемые файлы для 64 разрядной версии Windows 10 и 64 разрядной версии Mac OS X 10.11.
Система сборки создаст исполняемые файлы в машинном коде для текущей среды. Если выполнить эти действия на компьютере с Windows, будет создан исполняемый файл Windows. Если выполнить эти действия на компьютере с Mac OS, будет создан исполняемый файл OS X.

```json 
"runtimes": {
  "win10-x64": {},
  "osx.10.11-x64": {}
}
```

Полный список поддерживаемых сред выполнения см. в [каталоге RID](../rid-catalog.md). 
 
После внесения этих двух изменений следует выполнить команду `dotnet restore`, а затем команду `dotnet build`, чтобы создать исполняемый файл в машинном коде. Затем вы можете запустить созданный исполняемый файл в машинном коде. 

В приведенном ниже примере показаны команды для Windows. В примере показано, где создается исполняемый файл в машинном коде. В нем предполагается, что каталог проекта имеет имя HelloNative.

```
$ dotnet restore 
$ dotnet build 
$ .\bin\Debug\netcoreapp1.0\win10-x64\HelloNative.exe
Hello World!
```

Вы можете заметить, что сборка приложения в машинном коде идет немного дольше, но выполняется такое приложение немного быстрее. Эти отличия становятся заметнее по мере увеличения размера приложения.

При создании сборки в машинном коде процесс сборки `project.json` создает еще несколько файлов. Эти файлы создаются в каталоге `bin\Debug\netcoreapp1.0\<platform>`, где `<platform>` — выбранный идентификатор RID. Помимо файла `HelloNative.dll` проекта, имеется файл `HelloNative.exe`, который загружает среду выполнения и запускает приложение.
Обратите внимание на то, что имя созданного приложения изменилось, так как изменилось имя каталога проекта.  

Вам может потребоваться упаковать это приложение для выполнения на компьютере, на котором нет среды выполнения .NET.
Для этого служит команда `dotnet publish`. Команда `dotnet publish` создает подкаталог в каталоге `./bin/Debug/netcoreapp1.0/<platform>` с именем `publish`. Она копирует в этот подкаталог исполняемый файл, все зависимые библиотеки DLL и платформу. Вы можете упаковать этот каталог на другом компьютере (или в контейнере), чтобы выполнить приложение на нем. 

Давайте сравним это с поведением `dotnet publish` в первом примере Hello World. Первое приложение является *переносимым* — это тип приложений по умолчанию в .NET Core. Переносимое приложение требует установки .NET Core на целевом компьютере. Переносимые приложения можно создавать на одном компьютере, а выполнять на любых других. Приложения в машинном коде необходимо создавать отдельно для каждого целевого компьютера. `dotnet publish` создает каталог, содержащий библиотеку DLL приложения, а также все зависимые библиотеки DLL, не входящие в состав установки платформы.

### <a name="augmenting-the-program"></a>Расширение программы

Давайте немного изменим файл.  С числами Фибоначчи интересно работать, поэтому давайте попробуем сделать следующее (в версии в машинном коде):

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
$ .\bin\Debug\netcoreapp1.0\win10-x64\Fibonacci.exe
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
using static System.Console;
using NumberFun;
```

Наконец, можно выполнить сборку:

`$ dotnet build`

После этого наступает самое интересное — реализация задач, выполняемых файлом.

### <a name="example-a-fibonacci-sequence-generator"></a>Пример. Генератор последовательностей Фибоначчи

Предположим, что вы хотите использовать в качестве основы [предыдущий пример](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/Fibonacci), реализовав в нем кэширование значений Фибоначчи и рекурсию.  Код [улучшенного примера работы с числами Фибоначчи](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/FibonacciBetter) может выглядеть так:

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

Обратите внимание на то, что использование `Dictionary<int, int>` и `IEnumerable<int>` означает включение пространства имен `System.Collections`.
Пакет `Microsoft.NetCore.App` — это *метапакет*, который содержит многие базовые сборки платформы .NET Framework. Включив этот метапакет, вы уже включили сборку `System.Collections.dll` в состав проекта. Чтобы проверить это, выполните команду `dotnet publish` и просмотрите список файлов, входящих в установленный пакет. Файл `System.Collections.dll` присутствует в списке. 

```json
{ 
  "version": "1.0.0-*", 
  "buildOptions": { 
    "debugType": "portable", 
    "emitEntryPoint": true 
  }, 
  "dependencies": {}, 
  "frameworks": { 
    "netcoreapp1.0": { 
      "dependencies": { 
        "Microsoft.NETCore.App": { 
          "version": "1.0.0" 
        } 
      }, 
      "imports": "dnxcore50" 
    } 
  },
  "runtimes": {
    "win10-x64": {},
    "osx.10.11-x64": {}
  }
}
```

Теперь измените метод `Main()` в файле `Program.cs`, как показано ниже. В примере предполагается, что файл `Program.cs` содержит оператор `using System;`. Если оператор `using static System.Console;` имеется, удалите `Console.` из `Console.WriteLine`.  

```csharp
public static void Main(string[] args)
{
    var generator = new FibonacciGenerator();
    foreach (var digit in generator.Generate(15))
    {
        WriteLine(digit);
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

## <a name="using-folders-to-organize-code"></a>Упорядочение кода с помощью папок

Предположим, что требуется добавить новые типы для выполнения поставленных задач.  Это можно сделать путем добавления дополнительных файлов и назначения им пространств имен, которые можно включить в файл `Program.cs`.

```
/MyProject
|__Program.cs
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__project.json
```

такой подход работает, если размер проект относительно мал.  Однако если у вас большое приложение со множеством различных типов данных и, возможно, несколькими уровнями, вам может потребоваться логически упорядочить их.  Как раз для этого и могут пригодиться папки.  Вы можете разобрать [образец проекта NewTypes](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypes), который рассматривается в этом руководстве, или создать собственные файлы и папки.

Для начала создайте папку в корневом каталоге проекта.  В этом случае выбрано `/Model`.

```
/NewTypes
|__/Model
|__Program.cs
|__project.json
```

Далее добавьте в папку новые типы:

```
/NewTypes
|__/Model
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__Program.cs
|__project.json
```

Теперь присвойте им всем одно и то же пространство имен, как если бы они были файлами в одном каталоге, чтобы их можно было включить в файл `Program.cs`.

### <a name="example-pet-types"></a>Пример. Типы домашних животных

В этом примере создаются два типа, `Dog` и `Cat`, которые реализуют интерфейс `IPet`.

Структура папок:

```
/NewTypes
|__/Pets
   |__Dog.cs
   |__Cat.cs
   |__IPet.cs
|__Program.cs
|__project.json
```

`IPet.cs`:
```csharp
using System;

namespace Pets
{
    public interface IPet
    {
        string TalkToOwner();
    }
}
```

`Dog.cs`:
```csharp
using System;

namespace Pets
{
    public class Dog : IPet
    {
        public string TalkToOwner() => "Woof!";
    }
}
```

`Cat.cs`:
```csharp
using System;

namespace Pets
{
    public class Cat : IPet
    {
        public string TalkToOwner() => "Meow!";
    }
}
```

`Program.cs`:
```csharp
using System;
using Pets;
using System.Collections.Generic;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            List<IPet> pets = new List<IPet>
            {
                new Dog(),
                new Cat()  
            };
            
            foreach (var pet in pets)
            {
                Console.WriteLine(pet.TalkToOwner());
            }
        }
    }
}
```

`project.json`:
```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "emitEntryPoint": true
  },
  "dependencies": {
    "Microsoft.NETCore.App": {
      "type": "platform",
      "version": "1.0.0"
    }
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": "dnxcore50"
    }
  }
}
```

Если выполнить эту программу:

```
$ dotnet restore
$ dotnet run
Woof!
Meow!
```

Чтобы расширить проект, можно добавить новые типы домашних животных (например, `Bird`).

## <a name="testing-your-console-app"></a>Тестирование консольного приложения

На некотором этапе может потребоваться протестировать проект.  Вот как можно это сделать.

1. Переместите исходный код существующего проекта в новую папку `src`.

   ```
   /Project
   |__/src
   ```

2. Создайте каталог `/test`.

   ```
   /Project
   |__/src
   |__/test
   ```

3. Создайте файл `global.json`:

   ```
   /Project
   |__/src
   |__/test
   |__global.json
   ```

   `global.json`:
   ```json
   {
      "projects": [
         "src", "test"
      ]
   }
   ```

   Этот файл сообщает системе сборки, что это многопроектная система, что позволяет ей искать зависимости не только в текущей папке, в которой она выполняется.  Это важно, так как позволяет тестировать зависимость в коде тестового проекта.
   
### <a name="example-extending-the-newtypes-project"></a>Пример. Расширение проекта NewTypes

Теперь, когда вы реализовали систему проектов, можно создать тестовый проект и приступить к созданию тестов.  Далее в этом руководстве мы будем использовать и расширять [образец проекта Types](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypes).  Кроме того, будет использоваться платформа тестирования [Xunit](https://xunit.github.io/).  Вы можете рассмотреть этот пример или создать собственную многопроектную систему с тестами.


Структура проекта в целом должна выглядеть следующим образом:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__project.json
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__project.json
|__global.json
```

В тестовом проекте должно быть еще два новых компонента:

1. правильный файл `project.json` со следующими элементами:

   * ссылка на `xunit`
   * ссылка на `dotnet-test-xunit`
   * ссылка на пространство имен, соответствующее тестируемому коду;

2. класс теста Xunit.

`NewTypesTests/project.json`:
```json
{
  "version": "1.0.0-*",
  "testRunner": "xunit",

  "dependencies": {
    "Microsoft.NETCore.App": {
      "type":"platform",
      "version": "1.0.0"
    },
    "xunit":"2.2.0-beta2-build3300",
    "dotnet-test-xunit": "2.2.0-preview2-build1029",
    "NewTypes": "1.0.0"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "portable-net45+win8" 
      ]
    }
  }
}
```

`PetTests.cs`: 
```csharp
using System;
using Xunit;
using Pets;
public class PetTests
{
    [Fact]
    public void DogTalkToOwnerTest()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();
        
        Assert.Equal(expected, actual);
    }
    
    [Fact]
    public void CatTalkToOwnerTest()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();
           
        Assert.Equal(expected, actual);
    }
}
```
   
Теперь можно выполнить тесты.  Команда [`dotnet test`](../tools/dotnet-test.md) запускает средство выполнения тестов, которое вы указали в проекте. Начинать следует с каталога верхнего уровня.
 
```
$ dotnet restore
$ cd test/NewTypesTests
$ dotnet test
```
 
Выходные данные должны выглядеть следующим образом:
 
```
xUnit.net .NET CLI test runner (64-bit win10-x64)
  Discovering: NewTypesTests
  Discovered:  NewTypesTests
  Starting:    NewTypesTests
  Finished:    NewTypesTests
=== TEST EXECUTION SUMMARY ===
   NewTypesTests  Total: 2, Errors: 0, Failed: 0, Skipped: 0, Time: 0.144s
SUMMARY: Total: 1 targets, Passed: 1, Failed: 0.
```
 
## <a name="conclusion"></a>Заключение
 
Надеемся, это руководство помогло вам понять, как создавать консольные приложения .NET разного уровня сложности: от самых простых до многопроектных систем с модульными тестами.  Ваш следующий шаг — создание собственного консольного приложения.
 
Если вы хотите разобрать более подробный пример консольного приложения, обратитесь к следующему учебнику: [Подробное пошаговое руководство. Использование средств CLI для создания консольных приложений](cli-console-app-tutorial-advanced.md).



<!--HONumber=Feb17_HO2-->


