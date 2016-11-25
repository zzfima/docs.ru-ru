---
title: "Разработка приложений .NET Core"
description: "Разработка приложений .NET Core"
keywords: ".NET, .NET Core, разработка .NET Core"
author: rpetrusha
manager: wpickett
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: da7a31a0-8072-4f23-82aa-8a19184cb701
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: d99d1a68fd6d1daf68670d6d73c07fe1009d92d9

---

# <a name="net-core-application-deployment"></a>Разработка приложений .NET Core #

Для приложений .NET Core можно создавать два типа развертываний. 

- Развертывание, зависящее от платформы. Как понятно из названия, зависящее от платформы развертывание (FDD) требует наличия в целевой системе общей версии .NET Core. Так как платформа .NET Core уже имеется, приложение можно переносить между установками .NET Core. Приложение содержит только собственный код и зависимости сторонних разработчиков, которые не входят в библиотеки .NET Core. Зависящие от платформы развертывания содержат DLL-файл, которые можно запускать с помощью [служебной программы dotnet](../tools/dotnet.md) из командной строки. Например, команда `dotnet app.dll` запускает приложение с именем `app`.

- Автономные развертывания. В отличие от зависящих от платформы развертываний, автономное развертывание (SCD) не требует наличия в целевой системе каких-либо общих компонентов. Все компоненты, включая библиотеки .NET Core и среду выполнения .NET Core, включены в приложение и изолированы от других приложений .NET Core. Автономное развертывание включает в себя исполняемый файл (например, `app.exe` на платформах Windows для приложения с именем `app`), который является переименованной версией связанного с платформой узла .NET Core, и DLL-файл (например `app.dll`), представляющий собственно приложение.

## <a name="framework-dependent-deployments-fdd"></a>Развертывания, зависящие от платформы ##

В случае с зависящим от платформы развертыванием вы развертываете только приложение и зависимости сторонних разработчиков. Платформу .NET Core развертывать не нужно, так как приложение будет использовать версию .NET Core, имеющуюся в целевой системе. Это модель развертывания приложений .NET Core по умолчанию.

### <a name="why-create-a-framework-dependent-deployment"></a>Зачем использовать развертывание, зависящее от платформы ###

Развертывание, зависящее от платформы, имеет ряд преимуществ.

- Вам не нужно предварительно определять целевые операционные системы, в которых будет выполняться приложение .NET Core. Так как .NET Core использует общий формат файлов PE для исполняемых файлов и библиотек вне зависимости от операционной системы, ваше приложение может выполняться вне зависимости от базовой операционной системы. Дополнительные сведения о формате файлов PE см. в разделе [Формат файла сборки .NET](../../../standard/assembly-format.md).

- Пакет развертывания имеет небольшой размер. Необходимо развернуть только приложение и его зависимости, но не саму платформу .NET Core.

- Несколько приложений используют одну и ту же установку .NET Core, что сокращает использование дискового пространства и памяти в системе.

Имеется и ряд недостатков.

- Приложение может выполняться, только если в системе уже установлена целевая или более поздняя версия .NET Core.

- Среда выполнения и библиотеки .NET Core могут изменяться в будущих выпусках, о чем вы можете не знать. В редких случаях это может повлиять на работу вашего приложения.

### <a name="deploying-a-framework-dependent-deployment"></a>Выполнение развертывания, зависящего от платформы ###

Если развертывание, зависящее от платформы, не содержит зависимостей сторонних разработчиков, то необходимо просто выполнить сборку, протестировать и опубликовать приложение. Проиллюстрируем этот процесс на примере простого приложения, написанного на языке C#. В этом примере используется [программа командной строки dotnet](../tools/dotnet.md). однако вы также можете использовать среду развертывания, такую как Visual Studio или Visual Studio Code, для компиляции, тестирования и публикации приложения.

1. Создайте каталог для проекта, а затем в командной строке введите [dotnet new](../tools/dotnet-new.md), чтобы создать проект консольного приложения C#.

2. Откройте файл `Program.cs` в редакторе и замените автоматически созданный код приведенным ниже кодом. Он выводит запрос на ввод текста, а затем отображает отдельные слова, введенные пользователем. Для разделения слов во введенном тексте в нем используется регулярное выражение `\w+`.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else
              {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. Выполните команду [dotnet restore](../tools/dotnet-restore.md), чтобы восстановить зависимости, указанные в проекте.

4. Создайте отладочную сборку приложения с помощью команды [dotnet build](../tools/dotnet-build.md).

5. Отладив и протестировав программу, вы можете создать файлы, которые будут развертываться с приложением, с помощью команды `dotnet publish -f netcoreapp1.0 -c release`. При этом будет создана версия выпуска приложения (а не отладочная версия).

   Итоговые файлы помещаются в каталог с именем `publish`, который находится в подкаталоге каталога `.\bin\release\netcoreapp1.0` проекта.

6. Помимо файлов приложения, процесс публикации создает файл базы данных программы (PDB), который содержит отладочную информацию о приложении. Он служит в первую очередь для отладки исключений. Вы можете не упаковывать его вместе с файлами приложения.

Полный набор файлов приложения можно развернуть любым способом, каким вы хотите. Например, их можно упаковать в ZIP-файл, использовать простую команду `copy` или развернуть их с помощью любого установочного пакета на ваш выбор.

Помимо двоичных файлов приложения, установщик должен либо включать в себя установщик общей платформы, либо проверять наличие платформы в процессе установки приложения.  Установка общей платформы требует наличия прав администратор или root, так как она производится на уровне всего компьютера.

### <a name="deploying-a-framework-dependent-deployment-with-third-party-dependencies"></a>Выполнение развертывания, зависящего от платформы, с зависимостями сторонних разработчиков ###

Осуществление развертывания, зависящего от платформы, с одной или несколькими зависимостями сторонних разработчиков предполагает выполнение трех дополнительных действий перед выполнением команды `dotnet restore`.

1. Добавьте ссылки на библиотеки сторонних разработчиков в раздел `<ItemGroup>` файла `csproj`. В следующем разделе `<ItemGroup>` демонстрируется `<ItemGroup>`, где зависимости содержатся в проекте по умолчанию с файлом Json.NET в качестве сторонней библиотеки.

    ```xml
      <ItemGroup>
        <PackageReference Include="Microsoft.NETCore.App">
          <Version>1.0.1</Version>
        </PackageReference>
        <PackageReference Include="Newtonsoft.Json">
          <Version>9.0.1</Version>
        </PackageReference>
        <PackageReference Include="Microsoft.NET.Sdk">
          <Version>1.0.0-alpha-20161102-2</Version>
          <PrivateAssets>All</PrivateAssets>
        </PackageReference>
      </ItemGroup>
    ```

Обратите внимание, что в приведенном выше примере зависимость от пакета SDK остается. Это сделано преднамеренно, так как эта зависимость требуется для восстановления всех необходимых целевых объектов, чтобы обеспечить функционирование средств командной строки.  

2. Скачайте пакет NuGet, содержащий зависимость стороннего разработчика, если вы этого еще не сделали. Чтобы скачать пакет, выполните команду `dotnet restore` после добавления зависимости. Так как зависимость разрешается из локального кэша NuGet во время публикации, она должна быть доступна в системе.

Имейте в виду, что переносимость зависящего от платформы развертывания с зависимостями сторонних разработчиков напрямую зависит от переносимости этих зависимостей. Например, если библиотека стороннего разработчика поддерживает только Mac OS, приложение нельзя будет перенести в системы Windows. Это может происходить, если зависимость стороннего разработчика сама зависит от машинного кода. Хорошим примером этого является сервер Kestrel. Когда зависящее от платформы развертывание создается для приложения с таким типом зависимости стороннего разработчика, опубликованные выходные данные будут содержать папку для каждого [идентификатора среды выполнения (RID)](../../rid-catalog.md#what-are-rids), поддерживаемого зависимостью (и имеющегося в ее пакете NuGet).

## <a name="self-contained-deployments-scd"></a>Автономные развертывания ##

В случае с автономным развертыванием вы развертываете не только приложение и зависимости сторонних разработчиков, но и версию .NET Core, с помощью которой создавалось приложение. При создании автономного приложения, однако, не включаются [собственные зависимости .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) для различных платформ (например, OpenSSL для Mac OS), поэтому их надо установить перед запуском приложения. 

### <a name="why-deploy-a-self-contained-deployment"></a>Зачем использовать автономное развертывание ###

Автономное развертывание имеет два основных преимущества.

- Вы единолично контролируете версию .NET Core, которая развертывается вместе с приложением. Платформа .NET Core может предоставляться только вами.

- Вы можете быть уверены в том, что приложение .NET Core может выполняться в целевой системе, так как вы предоставили соответствующую версию .NET Core.

Есть также ряд недостатков.

- Так как платформа .NET Core включается в пакет развертывания, необходимо заранее выбрать целевые платформы, для которых вы создаете пакеты развертывания.

- Пакет развертывания имеет относительно большой размер, так как в него необходимо включить платформу .NET Core в дополнение к приложению и зависимостям сторонних разработчиков.

- При развертывании множества автономных приложений .NET Core в системе может использоваться значительный объем дискового пространства, так как каждое приложение создает копии файлов .NET Core.

### <a name="a-namesimpleselfa-deploying-a-simple-self-contained-deployment"></a><a name="simpleSelf"></a> Простое автономное развертывание ###

Выполнение автономного развертывания без зависимостей сторонних разработчиков предполагает создание проекта, изменение CSPROJ-файла, сборку, тестирование и публикацию приложения.  Проиллюстрируем этот процесс на примере простого приложения, написанного на языке C#. В этом примере используется программа командной строки `dotnet`, однако вы также можете использовать среду развертывания, такую как Visual Studio или Visual Studio Code, для компиляции, тестирования и публикации приложения.

1. Создайте каталог для проекта, а затем в командной строке введите `dotnet new`, чтобы создать проект консольного приложения C#.

2. Откройте файл `Program.cs` в редакторе и замените автоматически созданный код приведенным ниже кодом. Он выводит запрос на ввод текста, а затем отображает отдельные слова, введенные пользователем. Для разделения слов во введенном тексте в нем используется регулярное выражение `\w+`.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. В разделе `<PropertyGroup>` файла `csproj` создайте тег `<RuntimeIdentifiers>`, определяющий платформы, для которых предназначено приложение, и укажите идентификатор среды выполнения для каждой целевой платформы. Список идентификаторов сред выполнения см. в [каталоге идентификаторов сред выполнения](../../rid-catalog.md). Например, приведенный ниже раздел `runtimes` указывает, что приложение выполняется в 64-разрядной операционной системе Windows 10 и в 64-разрядной операционной системе OS X 10.11.

    ```xml
        <PropertyGroup>
          <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
        </PropertyGroup>
    ```
Обратите внимание, что для разделения идентификаторов RID необходимо добавлять точку с запятой. Также обратите внимание, что элемент `<RuntimeIdentifier>` можно переносить в другие группы `<PropertyGroup>` в пределах файла `csproj`. Полный образец файла `csproj` будет приведен далее в этом разделе.

4. Выполните команду `dotnet restore`, чтобы восстановить зависимости, указанные в проекте.

5. Создайте отладочные сборки приложения для каждой из целевых платформ с помощью команды `dotnet build`. Если не указать идентификатор среды выполнения, для которой нужно выполнить сборку, команда `dotnet build` создаст сборку только для идентификатора среды выполнения текущей системы. Чтобы выполнить сборку приложения для обеих целевых платформ, используйте следующие команды:

    ```console
    dotnet build -r win10-x64
    dotnet build -r osx.10.11-x64
    ```
Отладочные сборки приложения для каждой платформы будут находиться в подкаталоге `.\bin\Debug\netcoreapp1.0\<runtime_identifier>` проекта.

6. Отладив и протестировав программу, вы можете создать файлы, которые будут развертываться вместе с приложением для каждой целевой платформы с помощью команды `dotnet publish` следующим образом:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.11-x64
   ```
При этом будет создана версия выпуска приложения (а не отладочная версия) для каждой целевой платформы. Итоговые файлы помещаются в подкаталог с именем `publish`, который находится в подкаталоге каталога `.\bin\release\netcoreapp1.0\<runtime_identifier>` проекта. Обратите внимание на то, что каждый подкаталог содержит полный набор файлов (как файлов приложения, так и всех файлов .NET Core), необходимых для запуска приложения.

7. Помимо файлов приложения, процесс публикации создает файл базы данных программы (PDB), который содержит отладочную информацию о приложении. Он служит в первую очередь для отладки исключений. Вы можете не упаковывать его вместе с файлами приложения.

Опубликованные файлы можно развернуть любым способом, который вам нравится. Например, их можно упаковать в ZIP-файл, использовать простую команду `copy` или развернуть их с помощью любого установочного пакета на ваш выбор. 

Ниже приведено полное содержимое файла `csproj` для этого проекта.

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
    <DebugType>Portable</DebugType>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
      <Version>9.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161102-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```


### <a name="deploying-a-self-contained-deployment-with-third-party-dependencies"></a>Выполнение автономного развертывания с зависимостями сторонних разработчиков ###

Выполнение автономного развертывания с одной или несколькими зависимостями сторонних разработчиков предполагает добавление этих зависимостей.

1. Добавьте ссылки на библиотеки сторонних разработчиков в раздел `<ItemGroup>` файла `csproj`. В следующем разделе `<ItemGroup>` в качестве библиотеки стороннего разработчика используется библиотека Json.NET.

    ```xml
      <ItemGroup>
        <PackageReference Include="Microsoft.NETCore.App">
          <Version>1.0.1</Version>
        </PackageReference>
        <PackageReference Include="Microsoft.NET.Sdk">
          <Version>1.0.0-alpha-20161102-2</Version>
          <PrivateAssets>All</PrivateAssets>
        </PackageReference>
        <PackageReference Include="Newtonsoft.Json">
          <Version>9.0.1</Version>
        </PackageReference>
      </ItemGroup>
    ```
2. Скачайте пакет NuGet, содержащий зависимость стороннего разработчика, в систему, если вы этого еще не сделали. Чтобы сделать зависимость доступной для приложения, после ее добавления выполните команду `dotnet restore`. Так как зависимость разрешается из локального кэша NuGet во время публикации, она должна быть доступна в системе.

Ниже приведено полное содержимое CSPROJ-файла для этого проекта.

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
    <DebugType>Portable</DebugType>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
      <Version>9.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161102-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

При развертывании приложения все зависимости сторонних разработчиков, используемые в нем, также содержатся в файлах приложения. Библиотеки сторонних разработчиков не обязательно должны присутствовать в системе, в которой выполняется приложение.

Имейте в виду, что автономное развертывание с библиотекой стороннего разработчика возможно только на платформах, которые поддерживаются этой библиотекой. Это условие аналогично тому, что действует при наличии зависимостей сторонних разработчиков с собственными зависимостями при развертывании, зависящем от платформы. 

### <a name="deploying-a-self-contained-deployment-with-a-smaller-footprint"></a>Уменьшение размера автономного развертывания ###

Если в целевых системах может оказаться недостаточно дискового пространства, вы можете уменьшить общий размер приложения, исключив некоторые компоненты системы. Для этого следует явным образом определить компоненты .NET Core, которые приложение включает в CSPROJ-файл.

Чтобы создать автономное развертывание меньшего размера, сначала выполните первые два шага для создания автономного развертывания. Запустив команду `dotnet new` и добавив исходный код на языке C# в приложение, выполните указанные ниже действия.

1. Откройте файл `csproj` и замените раздел `frameworks` на следующий код:

    ```xml
    <PropertyGroup>
      <TargetFramework>netstandard1.6</TargetFramework>
  </PropertyGroup>
  ```
Эта операция указывает на то, что вместо использования всей платформы `netcoreapp1.0`, включающей среду CLR .NET Core, библиотеку .NET Core и ряд других системных компонентов, наше приложение использует только библиотеку .NET Standard.

2. Замените раздел `dependencies` на следующий код:

    ```xml
    <ItemGroup>
      <PackageReference Include="NETSTandard.Library">
        <Version>1.6.0</Version>
      </PackageReference>
      <PackageReference Include="Microsoft.NETCore.Runtime.CoreCLR">
        <Version>1.0.2</Version>
      </PackageReference>
      <PackageReference Include="Microsoft.NETCore.DotNetHostPolicy">
        <Version>1.0.1</Version>
      </PackageReference>
      <PackageReference Include="Microsoft.NET.Sdk">
        <Version>1.0.0-alpha-20161102-2</Version>
        <PrivateAssets>All</PrivateAssets>
      </PackageReference>
    </ItemGroup>
  ```

   Он определяет компоненты системы, используемые приложением. К компонентам системы, упаковываемым вместе с приложением, относятся библиотека .NET Standard, среда выполнения .NET Core и узел .NET Core. В результате получается автономное развертывание меньшего размера.

3. Так же, как в примере [Выполнение простого автономного развертывания](#simpleSelf), создайте элемент `<RuntimeIdentifiers>` в разделе `<PropertyGroup>` файла `csproj`, определяющий платформы, для которых предназначено приложение, и укажите идентификатор среды выполнения для каждой целевой платформы. Список идентификаторов сред выполнения см. в [каталоге идентификаторов сред выполнения](../../rid-catalog.md). Например, приведенный ниже пример указывает, что приложение выполняется в 64-разрядной операционной системе Windows 10 и в 64-разрядной операционной системе OS X 10.11.

    ```xml
        <PropertyGroup>
          <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
        </PropertyGroup>
    ```
    

Полный образец файла `csproj` будет приведен далее в этом разделе.

4. Выполните команду `dotnet restore`, чтобы восстановить зависимости, указанные в проекте.

5. Создайте отладочные сборки приложения для каждой из целевых платформ с помощью команды `dotnet build`. Если не указать идентификатор среды выполнения, для которой нужно выполнить сборку, команда `dotnet build` создаст сборку только для идентификатора среды выполнения текущей системы. Чтобы выполнить сборку приложения для обеих целевых платформ, используйте следующие команды:

    ```console
    dotnet build -r win10-x64
    dotnet build -r osx.10.11-x64
    ```

6. Отладив и протестировав программу, вы можете создать файлы, которые будут развертываться вместе с приложением для каждой целевой платформы с помощью команды `dotnet publish` следующим образом:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.11-x64
   ```
При этом будет создана версия выпуска приложения (а не отладочная версия) для каждой целевой платформы. Итоговые файлы помещаются в подкаталог с именем `publish`, который находится в подкаталоге каталога `.\bin\release\netstandard1.6\<runtime_identifier>` проекта. Обратите внимание на то, что каждый подкаталог содержит полный набор файлов (как файлов приложения, так и всех файлов .NET Core), необходимых для запуска приложения.

7. Помимо файлов приложения, процесс публикации создает файл базы данных программы (PDB), который содержит отладочную информацию о приложении. Он служит в первую очередь для отладки исключений. Вы можете не упаковывать его вместе с файлами приложения.

Опубликованные файлы можно развернуть любым способом, который вам нравится. Например, их можно упаковать в ZIP-файл, использовать простую команду `copy` или развернуть их с помощью любого установочного пакета на ваш выбор. 

Ниже приведено полное содержимое файла `csproj` для этого проекта.

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
    <DebugType>Portable</DebugType>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="NETSTandard.Library">
      <Version>1.6.0</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NETCore.Runtime.CoreCLR">
      <Version>1.0.2</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NETCore.DotNetHostPolicy">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161102-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```




<!--HONumber=Nov16_HO3-->


