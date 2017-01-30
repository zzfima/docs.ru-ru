---
title: "Справочник по файлу project.json"
description: "Справочник по файлу project.json"
keywords: .NET, .NET Core, project.json
author: aL3891
ms.author: mairaw
ms.date: 12/21/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 3aef32bd-ee2a-4e24-80f8-a2b615e0336d
translationtype: Human Translation
ms.sourcegitcommit: 4023c5ec72055fee78863a43b60989e1eb34fb22
ms.openlocfilehash: 68b152cda54b5356dce48f4a8330b2ecb9c9d2e0

---

# <a name="projectjson-reference"></a>Справочник по файлу project.json

Файл project.json используется в проектах .NET Core для определения метаданных проекта, сведений о компиляции и зависимостей. В этом справочном разделе приводится список всех свойств, которые можно определить в файле project.json.

> [!NOTE]
> В будущих выпусках средств .NET Core будут переводиться с использования файлов project.json на проекты на основе MSBuild. Для новых проектов .NET Core рекомендуется по-прежнему использовать файлы project.json, так как при выпуске новых средств будет предложен способ преобразования проектов в MSBuild.
>
> Дополнительные сведения см. в записи [Изменения в файле project.json](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) в блоге по .NET и в разделе [Использование системы MSBuild для сборки проектов .NET Core](../tutorials/target-dotnetcore-with-msbuild.md).

## <a name="overview"></a>Обзор

```
{
    "name": String,
    "version": String,
    "description": String,
    "copyright": String,
    "title": String,
    "entryPoint": String,
    "testRunner": String,
    "authors": String[],
    "language": String,
    "embedInteropTypes": Boolean,
    "preprocess": String or String[],
    "shared": String or String[],
    "dependencies": Object {
        version: String,
        type: String,
        target: String,
        include: String,
        exclude: String,
        suppressParent: String
    },
    "tools": Object,
    "scripts": Object,
    "buildOptions": Object {
        "define": String[],
        "nowarn": String[],
        "additionalArguments": String[],
        "warningsAsErrors": Boolean,
        "allowUnsafe": Boolean,
        "emitEntryPoint": Boolean,
        "optimize": Boolean,
        "platform": String,
        "languageVersion": String,
        "keyFile": String,
        "delaySign": Boolean,
        "publicSign": Boolean,
        "debugType": String,
        "xmlDoc": Boolean,
        "preserveCompilationContext": Boolean,
        "outputName": String,
        "compilerName": String,
        "compile": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        },
        "embed": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        },
        "copyToOutput": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        }
    },
    "publishOptions": Object {
        "include": String or String[],
        "exclude": String or String[],
        "includeFiles": String or String[],
        "excludeFiles": String or String[],
        "builtIns": Object,
        "mappings": Object
    },
    "runtimeOptions": Object {
        "configProperties": Object {
            "System.GC.Server": Boolean,
            "System.GC.Concurrent": Boolean,
            "System.GC.RetainVM": Boolean,
            "System.Threading.ThreadPool.MinThreads": Integer,
            "System.Threading.ThreadPool.MaxThreads": Integer
        },
        "framework": Object {
            "name": String,
            "version": String,
        },
        "applyPatches": Boolean
    },
    "packOptions": Object {
        "summary": String,
        "tags": String[],
        "owners": String[],
        "releaseNotes": String,
        "iconUrl": String,
        "projectUrl": String,
        "licenseUrl": String,
        "requireLicenseAcceptance": Boolean,
        "repository": Object {
            "type": String,
            "url": String
        },
        "files": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        }
    },
    "analyzerOptions": Object {
        "languageId": String
    },
    "configurations": Object,
    "frameworks": Object {
        "dependencies": Object {
            version: String,
            type: String,
            target: String,
            include: String,
            exclude: String,
            suppressParent: String
        },        
        "frameworkAssemblies": Object,
        "wrappedProject": String,
        "bin": Object {
            assembly: String
        }
    },
    "runtimes": Object,
    "userSecretsId": String
}
```

## <a name="name"></a>имя
Тип данных: String

Имя проекта, используемое в качестве имени сборки, а также имени пакета. Если значение не указано, используется имя папки верхнего уровня.

Пример:

```json
{
    "name": "MyLibrary"
}
```

## <a name="version"></a>version
Тип данных: String

Версия [Semver](http://semver.org/spec/v1.0.0.html) проекта, также используемая для пакета NuGet.

Пример:

```json
{
    "version": "1.0.0-*"
}
```

## <a name="description"></a>описание
Тип данных: String

Более подробное описание проекта. Используется в свойствах сборки.

Пример:

```json
{
    "description": "This is my library and it's really great!"
}
```

## <a name="copyright"></a>авторские права
Тип данных: String

Сведения об авторских правах на проект. Используется в свойствах сборки.

Пример:

```json
{
    "copyright": "Fabrikam 2016"
}
```

## <a name="title"></a>заголовок
Тип данных: String

Понятное имя проекта; может содержать пробелы и специальные символы, недопустимые при использовании свойства `name`. Используется в свойствах сборки.

Пример:

```json
{
    "title": "My Library"
}
```

## <a name="entrypoint"></a>entryPoint
Тип данных: String

Метод entryPoint для проекта. По умолчанию: `Main`.

Например:

```json
{
    "entryPoint": "ADifferentMethod"
}
```
    
## <a name="testrunner"></a>testRunner
Тип данных: String

Имя средства запуска тестов (например, [NUnit](http://nunit.org/) или [xUnit](http://xunit.github.io/)), которое необходимо использовать для проекта. При задании этого значения проект помечается как тестовый.

Пример:

```json
{
    "testRunner": "NUnit"
}
```

## <a name="authors"></a>authors
Тип данных: String[]

Массив строк, представляющих имена разработчиков проекта.

Пример:

```json
{
    "authors": ["Anne", "Bob"]
}
```

## <a name="language"></a>язык
Тип данных: String

Язык проекта (естественный). Соответствует аргументу neutral-language компилятора.

Пример:

```json
{
    "language": "en-US"
}
```

## <a name="embedinteroptypes"></a>embedInteropTypes
Тип данных: Boolean

`false` — для внедрения типов COM-взаимодействия в сборку; в противном случае — `true`. 

Например:

```json
{
    "embedInteropTypes": true
}
```

## <a name="preprocess"></a>preprocess
Тип данных: String или String[] с шаблоном глобализации

Указывает, какие файлы подвергаются предварительной обработке.

Пример:

```json
{
    "preprocess": "compiler/preprocess/**/*.cs"
}
```

## <a name="shared"></a>общие
Тип данных: String или String[] с шаблоном глобализации

Указывает, какие файлы являются общими; используется для экспорта библиотек.

Пример:

```json
{
    "shared": "shared/**/*.cs"
}
```

## <a name="dependencies"></a>зависимости
Тип данных: Object

Объект, который определяет зависимости пакетов в проекте. Каждый ключ этого объекта представляет имя пакета, а каждое значение содержит сведения об управлении версиями.
Дополнительные сведения см. в статье [Разрешение зависимостей](https://docs.nuget.org/ndocs/consume-packages/dependency-resolution#dependency-resolution-in-nuget-3-x) на сайте документации по NuGet.

Пример:

```json
    "dependencies": {
        "System.Reflection.Metadata": "1.3.0",
        "Microsoft.Extensions.JsonParser.Sources": {
          "type": "build",
          "version": "1.0.0-rc2-20221"
        },
        "Microsoft.Extensions.HashCodeCombiner.Sources": {
          "type": "build",
          "version": "1.1.0-alpha1-21456"
        },
        "Microsoft.Extensions.DependencyModel": "1.0.0-*"
    }
```

### <a name="version"></a>version
Тип данных: String

Указывает версию или диапазон версий зависимости. Чтобы указать [нефиксированную версию зависимости](https://docs.nuget.org/ndocs/consume-packages/dependency-resolution#floating-versions), используйте подстановочный знак \*.

Пример:

```json
"dependencies": { 
    "Newtonsoft.Json": { 
        "version": "9.0.1" 
    }
}
```

### <a name="type"></a>type
Тип данных: String

Определяет тип зависимости. Может принимать одно из следующих значений: `default`, `build` или `platform`. Значение по умолчанию — `default`.

`build` называется зависимостью времени разработки и используется только во время разработки. Означает, что пакет не должен публиковаться или добавляться в качестве зависимости в выходной файл `.nupkg`. Эффект тот же, что и при присвоении свойству [supressParent](#supressparent) значения `all`.

`platform` ссылается на общий пакет SDK. Дополнительные сведения см. в подразделе "Выполнение развертывания, зависящего от платформы, с зависимостями сторонних разработчиков" раздела [Развертывание приложений .NET Core](../deploying/index.md).

Например:

```json
 "dependencies": {
   "Microsoft.NETCore.App": {
     "type": "platform",
     "version": "1.0.0"
   }
 }
```

### <a name="target"></a>целевой объект
Тип данных: String

Ограничивает зависимость так, что он может соответствовать только `project` или `package`.

### <a name="include"></a>include
Тип данных: String

Включает части пакетов зависимостей. Можно использовать один или несколько следующих флагов: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` или `none`.
Несколько флагов устанавливаются в виде списка, разделенного запятыми.
Дополнительные сведения см. в спецификации [Управление ресурсами пакетов зависимостей](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) в репозитории NuGet.

Пример:

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "include": "runtime"
    }
  }
}
```

### <a name="exclude"></a>exclude
Тип данных: String

Исключает части пакетов зависимостей. Можно использовать один или несколько следующих флагов: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` или `none`.
Несколько флагов устанавливаются в виде списка, разделенного запятыми.
Дополнительные сведения см. в спецификации [Управление ресурсами пакетов зависимостей](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) в репозитории NuGet.

Пример:

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "exclude": "contentFiles"
    }
  }
}
```

### <a name="supressparent"></a>supressParent
Тип данных: String

Определяет дополнительные исключения для потребителей проекта. Можно использовать один из следующих флагов: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` или `none`.
Дополнительные сведения см. в спецификации [Управление ресурсами пакетов зависимостей](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) в репозитории NuGet.

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "suppressParent": "compile"
    }
  }
}
```

## <a name="tools"></a>средства
Тип данных: Object

Объект, определяющий зависимости пакетов, которые используются в качестве средств для текущего проекта, а не как ссылки. Определенные в этом свойстве пакеты доступны в скриптах, которые выполняются в процессе сборки, но недоступны для кода в самом проекте. Средствами могут быть, например, генераторы кода или средства, которые выполняют задачи, связанные с упаковкой, после сборки.

Пример:

```json
{
    "tools": {
    "MyObfuscator": "1.2.4"
    }
}
```

## <a name="scripts"></a>scripts
Тип данных: Object

Объект, определяющий скрипты, которые выполняются в процессе сборки. Каждый ключ в этом объекте определяет место в сборке, в котором выполняется скрипт. Каждое значение представляет собой либо строку с выполняемым скриптом, либо массив строк, содержащих скрипты в порядке их выполнения.
Поддерживаемые события:
* precompile
* postcompile
* prepublish
* postpublish

Пример:

```json
{
    "scripts": {
        "precompile": "generateCode.cmd",
        "postcompile": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
    }
}
```

## <a name="buildoptions"></a>buildOptions
Тип данных: Object

Объект, свойства которого контролируют различные аспекты компиляции. Ниже перечислены допустимые свойства. Может также указываться для отдельных целевых платформ, как описано в [разделе, посвященном платформам](#frameworks).

Пример:

```json
    "buildOptions": {
      "allowUnsafe": true,
      "emitEntryPoint": true
    }
```

### <a name="define"></a>define
Тип данных: String[]

Список определений, например DEBUG или TRACE, которые могут использоваться при условной компиляции кода.

Пример:

```json
{
    "buildOptions": {
        "define": ["TEST", "OTHERCONDITION"]
    }
}
```

### <a name="nowarn"></a>nowarn
Тип данных: String[]

Список игнорируемых предупреждений.

Например:

```json
{
    "buildOptions": {
        "nowarn": ["CS0168", "CS0219"]
    }
}
```

Игнорируются предупреждения `The variable 'var' is declared but never used` и `The variable 'var' is assigned but its value is never used`.

### <a name="additionalarguments"></a>additionalArguments
Тип данных: String[]

Список дополнительных аргументов, которые будут переданы компилятору.

Пример:

```json
{
    "buildOptions": {
        "additionalArguments": ["/parallel", "/nostdlib"]
    }
}
```

### <a name="warningsaserrors"></a>warningsAsErrors
Тип данных: Boolean

`true` — для обработки всех предупреждений как ошибок; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "warningsAsErrors": true
    }
}
```

### <a name="allowunsafe"></a>allowUnsafe
Тип данных: Boolean

`true` для разрешения небезопасного кода в проекте; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "allowUnsafe": true
    }
}
```

### <a name="emitentrypoint"></a>emitEntryPoint
Тип данных: Boolean

`true` — для создания исполняемого файла; `false` — для создания библиотеки. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "emitEntryPoint": true
    }
}
```

### <a name="optimize"></a>optimize
Тип данных: Boolean

`true` разрешает компилятору оптимизировать код в проекте; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "optimize": true
    }
}
```

### <a name="platform"></a>platform
Тип данных: String

Имя целевой платформы, например AnyCpu, x86 или x64.

Пример:

```json
{
    "buildOptions": {
        "platform": "x64"
    }
}
```

### <a name="languageversion"></a>languageVersion
Тип данных: String

Версия языка, используемая компилятором: ISO-1, ISO-2, 3, 4, 5, 6 или Default.

Пример:

```json
{
    "buildOptions": {
        "languageVersion": "5"
    }
}
```

### <a name="keyfile"></a>keyFile
Тип данных: String

Путь к файлу ключа, используемому для подписания этой сборки.

Пример:

```json
{
    "buildOptions": {
        "keyFile": "../keyfile.snk"
    }
}
```

### <a name="delaysign"></a>delaySign
Тип данных: Boolean

`true` откладывает подписание; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "delaySign": true
    }
}
```

### <a name="publicsign"></a>publicSign
Тип данных: Boolean

`true` включает подписание итоговой сборки; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "publicSign": true
    }
}
```

### <a name="debugtype"></a>debugType
Тип данных: String

Указывает тип создаваемого файла символов (PDB-файла). Возможные значения: portable (для проектов .NET Core) или full (традиционные PDB-файлы, поддерживаемые только в Windows).

Пример:

```json
{
    "buildOptions": {
        "debugType": "portable"
    }
}
```

### <a name="xmldoc"></a>xmlDoc
Тип данных: Boolean

`false` создает документацию в формате XML на основе комментариев с тройной косой чертой в исходном коде; в противном случае — значение `true`. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "xmlDoc": true
    }
}
```

### <a name="preservecompilationcontext"></a>preserveCompilationContext
Тип данных: Boolean

`true` для сохранения ссылочных сборок и других контекстных данных с целью обеспечения компиляции во время выполнения; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "buildOptions": {
        "preserveCompilationContext": true
    }
}
```

### <a name="outputname"></a>outputName
Тип данных: String

Изменяет имя выходного файла. 

Пример:

```json
{
    "buildOptions": {
        "outputName": "MyApp"
    }
}
```

### <a name="compilername"></a>compilerName
Тип данных: String

Имя компилятора, используемого для проекта. По умолчанию: `csc`. В настоящее время поддерживаются значения `csc` (компилятор C#) и `fsc` (компилятор F#).
 
Пример:

```json
{
    "compilerName": "fsc"
}
```
    
### <a name="compile"></a>compile
Тип данных: Object

Объект, содержащий свойства для конфигурации компиляции.

#### <a name="include"></a>include
Тип данных: String или String[] с шаблоном подстановки.

Указывает, какие файлы следует включить в сборку. Папка проекта является корневой для шаблонов. Значение по умолчанию — none.

Пример:

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Тип данных: String или String[] с шаблоном подстановки.

Указывает, какие файлы следует исключить из сборки. Шаблоны исключения имеют более высокий приоритет, чем шаблоны включения, поэтому файл, указанный в обоих шаблонах, будет исключен. Папка проекта является корневой для шаблонов. Значение по умолчанию — none.

Пример:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Тип данных: String или String[] с шаблоном подстановки.

Список включаемых путей к файлам. Папка проекта является корневой для путей. Этот список имеет более высокий приоритет, чем шаблоны подстановки включения и исключения, поэтому файл, указанный в нем и в шаблоне подстановки исключения, будет включен. Значение по умолчанию — none.

Пример:

```json
{
    "includeFiles": []
}
```

#### <a name="excludefiles"></a>excludeFiles

Тип данных: String или String[] с шаблоном подстановки.

Список исключаемых путей к файлам. Папка проекта является корневой для путей. Этот список имеет более высокий приоритет, чем шаблоны подстановки и пути включения, поэтому файл, указанный во всех шаблонах и путях, будет исключен. Значение по умолчанию — none.

Пример:

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns

Тип данных: Object

Значения по умолчанию, предоставляемые системой. Может содержать шаблоны подстановки `include` и `exclude`, которые объединяются с соответствующими значениями свойств `include` и `exclude`.

Пример:

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>сопоставления
Тип данных: Object

Ключи объекта представляют пути назначения в структуре выходных данных.

Значением может быть либо строка, либо объект, представляющий исходный путь ко включаемым файлам.  Представление в виде объекта может иметь собственные разделы `include`, `exclude`, `includeFiles` и `excludeFiles`.

Пример строки:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Пример объекта:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

### <a name="embed"></a>embed
Тип данных: Object

Объект, содержащий свойства для конфигурации компиляции.

#### <a name="include"></a>include
Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Тип данных: String или String[] с шаблоном подстановки.

Указывает, какие файлы следует исключить из сборки.

Пример:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "includeFiles":[],
}
```

#### <a name="excludefiles"></a>excludeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns
Тип данных: Object

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>сопоставления
Тип данных: Object

Ключи объекта представляют пути назначения в структуре выходных данных.

Значением может быть либо строка, либо объект, представляющий исходный путь ко включаемым файлам.  Представление в виде объекта может иметь собственные разделы `include`, `exclude`, `includeFiles` и `excludeFiles`.

Пример строки:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Пример объекта:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

### <a name="copytooutput"></a>copyToOutput
Тип данных: Object

Объект, содержащий свойства для конфигурации компиляции.

#### <a name="include"></a>include
Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Тип данных: String или String[] с шаблоном подстановки.

Указывает, какие файлы следует исключить из сборки.

Пример:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "includeFiles":[],
}
```

#### <a name="excludefiles"></a>excludeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns
Тип данных: Object

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>сопоставления
Тип данных: Object

Ключи объекта представляют пути назначения в структуре выходных данных.

Значением может быть либо строка, либо объект, представляющий исходный путь ко включаемым файлам.  Представление в виде объекта может иметь собственные разделы `include`, `exclude`, `includeFiles` и `excludeFiles`.

Пример строки:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Пример объекта:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

## <a name="publishoptions"></a>publishOptions
Тип данных: Object

Объект, содержащий свойства для конфигурации компиляции.

### <a name="include"></a>include
Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "include":["wwwroot", "Views"]
}
```

### <a name="exclude"></a>exclude
Тип данных: String или String[] с шаблоном подстановки.

Указывает, какие файлы следует исключить из сборки.

Пример:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

### <a name="includefiles"></a>includeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "includeFiles":[],
}
```

### <a name="excludefiles"></a>excludeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "excludeFiles":[],
}
```

### <a name="builtins"></a>builtIns
Тип данных: Object

```json
{
    "builtIns":{}
}
```

### <a name="mappings"></a>сопоставления
Тип данных: Object

Ключи объекта представляют пути назначения в структуре выходных данных.

Значением может быть либо строка, либо объект, представляющий исходный путь ко включаемым файлам.  Представление в виде объекта может иметь собственные разделы `include`, `exclude`, `includeFiles` и `excludeFiles`.

Пример строки:

```json
{
    "mappings": {
        "dest/file": "./src/file",
        "dest/folder/": "./src/folder/**/*"
    }
}
```

Пример объекта:

```json
{
    "mappings": {
        "dest/file":{
            "include":"./src/file"
        },
        "dest/folder/":{
            "include":"./src/folder/**/*"
        }
    }
}
```

## <a name="runtimeoptions"></a>runtimeOptions
Тип данных: Object

Задает параметры, которые предоставляются среде выполнения во время инициализации.

### <a name="configproperties"></a>configProperties
Тип данных: Object

Содержит свойства конфигурации для настройки среды выполнения и платформы.

#### <a name="systemgcserver"></a>System.GC.Server
Тип данных: Boolean

`true` — включение сборки мусора на сервере; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.Server": true
        }
    }
}
```

#### <a name="systemgcconcurrent"></a>System.GC.Concurrent
Тип данных: Boolean

`true` — включение параллельной сборки мусора; в противном случае — значение `false`. Значение по умолчанию — `false`.

Пример:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.Concurrent": true
        }
    }
}
```

#### <a name="systemgcretainvm"></a>System.GC.RetainVM
Тип данных: Boolean

`true` — помещение сегментов, которые следует удалить, в список ожидания с целью использования в будущем вместо их возврата операционной системе; в противном случае — значение `false`.
Значение по умолчанию — `false`.

Пример:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.RetainVM": true
        }
    }
}
```

#### <a name="systemthreadingthreadpoolminthreads"></a>System.Threading.ThreadPool.MinThreads
Тип данных: Integer

Переопределяет минимальное число потоков для рабочего пула ThreadPool.

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.Threading.ThreadPool.MinThreads": 4
        }
    }
}
```

#### <a name="systemthreadingthreadpoolmaxthreads"></a>System.Threading.ThreadPool.MaxThreads
Тип данных: Integer

Переопределяет максимальное число потоков для рабочего пула ThreadPool.

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.Threading.ThreadPool.MaxThreads": 25
        }
    }
}
```

### <a name="framework"></a>платформа
Тип данных: Object

Содержит свойства общей платформы, используемые при активации приложения. Наличие этого раздела означает, что приложение является переносимым и предназначено для использования общей распространяемой платформы.

#### <a name="name"></a>имя
Тип данных: String

Имя общей платформы.

```json
{
    "runtimeOptions": {
        "framework": {
            "name": "Microsoft.DotNetCore"
        }
    }
}
```

#### <a name="version"></a>version
Тип данных: String

Версия общей платформы.

```json
{
    "runtimeOptions": {
        "framework": {
            "version": "1.0.1"
        }
    }
}
```

### <a name="applypatches"></a>applyPatches
Тип данных: Boolean

`true` — использование платформы той же или более поздней версии, которая отличается только полем исправления `SemVer`. `false` — использование узлом только точно определенной версии платформы. Значение по умолчанию — `true`.

```json
{
    "runtimeOptions": {
        "applyPatches": false
    }
}
```

## <a name="packoptions"></a>packOptions
Тип данных: Object

Определяет параметры, относящиеся к упаковке выходных данных проекта в пакет NuGet.

### <a name="summary"></a>сводка
Тип данных: String

Краткое описание проекта.

Пример:

```json
{
    "packOptions": {
        "summary": "This is my library."
    }
}
```

### <a name="tags"></a>теги
Тип данных: String[]

Массив строк с тегами для проекта, используемыми для поиска в NuGet.

Пример:

```json
{
    "packOptions": {
        "tags": ["hyperscale", "cats"]
    }
}
```

### <a name="owners"></a>owners
Тип данных: String[]

Массив строк с именами владельцев проекта.

Пример:

```json
{
    "packOptions": {
        "owners": ["Fabrikam", "Microsoft"]
    }
}
```

### <a name="releasenotes"></a>releaseNotes
Тип данных: String

Заметки о выпуске для проекта.

Пример:

```json
{
    "packOptions": {
        "releaseNotes": "Initial version, implemented flimflams."
    }
}
```

### <a name="iconurl"></a>iconUrl
Тип данных: String

URL-адрес значка, который будет использоваться в различных местах, например в обозревателе пакетов.

Пример:

```json
{
    "packOptions": {
        "iconUrl": "http://www.mylibrary.gov/favicon.ico"
    }
}
```

### <a name="projecturl"></a>projectUrl
Тип данных: String

URL-адрес домашней страницы проекта.

Пример:

```json
{
    "packOptions": {
        "projectUrl": "http://www.mylibrary.gov"
    }
}
```

### <a name="licenseurl"></a>licenseUrl
Тип данных: String

URL-адрес лицензии, используемой проектом.

Пример:

```json
{
    "packOptions": {
        "licenseUrl": "http://www.mylibrary.gov/licence"
    }
}
```

### <a name="requirelicenseacceptance"></a>requireLicenseAcceptance
Тип данных: Boolean

`true` выводит запрос на принятие условий лицензии пакета при его установке; в противном случае — значение `false`. Используется только для пакетов NuGet; в остальных случаях игнорируется. Значение по умолчанию — `false`.

Пример:

```json
{
    "packOptions": {
        "requireLicenseAcceptance": true
    }
}
```
   
### <a name="repository"></a>репозиторий
Тип данных: Object

Содержит сведения о репозитории, в котором хранится проект.

#### <a name="type"></a>type
Тип данных: String

Тип репозитория. Значение по умолчанию — git.

Пример:

```json
{
    "packOptions": {
        "repository": {
            "type": "git"
        }
    }
}
```

#### <a name="url"></a>url
Тип данных: String

URL-адрес репозитория, в котором хранится проект.

Пример:

```json
{
    "packOptions": {
        "repository": {
            "url": "http://github.com/dotnet/corefx"
        }
    }
}
```

### <a name="files"></a>файлы
Тип данных: Object

#### <a name="include"></a>include
Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Тип данных: String или String[] с шаблоном подстановки.

Указывает, какие файлы следует исключить из сборки.

Пример:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "includeFiles":[]
}
```

#### <a name="excludefiles"></a>excludeFiles

Тип данных: String или String[] с шаблоном подстановки.

```json
{
    "excludeFiles":[]
}
```

#### <a name="builtins"></a>builtIns
Тип данных: Object

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>сопоставления
Тип данных: Object

Ключи объекта представляют пути назначения в структуре выходных данных.

Значением может быть либо строка, либо объект, представляющий исходный путь ко включаемым файлам.  Представление в виде объекта может иметь собственные разделы `include`, `exclude`, `includeFiles` и `excludeFiles`. 

Пример строки:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Пример объекта:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

## <a name="analyzeroptions"></a>analyzerOptions
Тип данных: Object

Объект со свойствами, используемыми анализаторами кода.

Пример:

```json
{
    "analyzerOptions": { }
}
```

### <a name="languageid"></a>languageId
Тип данных: String

Идентификатор анализируемого языка. cs представляет язык C#, vb — язык Visual Basic, а fs — язык F#.

Пример:

```json
"analyzerOptions": {
    "languageId": "vb"
}
```

## <a name="configurations"></a>конфигурации
Тип данных: Object

Объект, свойства которого определяют различные конфигурации для этого проекта, например отладки и выпуска. Каждое значение — это объект, который может содержать объект `buildOptions` с параметрами, относящимися к этой конфигурации.

Пример:

```json
"configurations": {
    "Release": {
        "buildOptions": {
            "allowUnsafe": false
        }
    }
}
```

## <a name="frameworks"></a>Инфраструктуры
Тип данных: Object

Указывает платформы, которые поддерживает этот проект, например .NET Framework или универсальную платформу Windows (UWP). Значение должно быть допустимым моникером целевой платформы (TFM). Каждое значение — это объект, который может содержать сведения, относящиеся к этой среде, например `buildOptions`, `analyzerOptions`, `dependencies`, а также свойства в следующих разделах.

Пример:

```json
"frameworks": {
    "netcoreapp1.0": {
        "buildOptions": {
            "define": ["FOO", "BIZ"]
        }
    }
}
```

### <a name="dependencies"></a>зависимости
Тип данных: Object

Зависимости, характерные для платформы. Это полезно в сценариях, в которых нельзя просто указать зависимость на уровне пакета для всех целевых платформ. Причинами могут быть отсутствие у одной из целевых платформ встроенной поддержки, которая есть у других целевых платформ, или потребность в другой версии зависимости, отличной от версий других целевых платформ. Чтобы просмотреть список других свойств для этого узла, см. предыдущий раздел [dependencies](#dependencies).

Пример:

```json
    "frameworks": {
        "netstandard1.5": {
        "dependencies": {
            "Microsoft.Extensions.JsonParser.Sources": "1.0.0-rc2-20221"
        }
    }
}
```

### <a name="frameworkassemblies"></a>frameworkAssemblies
Тип данных: Object

Аналогично свойству dependencies, но содержит ссылки на сборки в глобальном кэше сборок, которые не являются пакетами NuGet. Может также указывать версию, которую необходимо использовать, и тип зависимости. Используется при нацеливании на .NET Framework и библиотеку переносимых классов (PCL). Выполнить сборку проекта с этим значением можно только в Windows.

Пример:

```json
"frameworks": {
    "net451": {
        "frameworkAssemblies": {
            "System.Runtime": {
                "type": "build",
                "version": "4.0.0"
            }
        }
    }
}
```

### <a name="wrappedproject"></a>wrappedProject
Тип данных: String

Задает расположение проекта зависимости. 

Пример:

```json
"frameworks": {
    "net451": {
        "wrappedProject": "MyProject.csproj"
    }
}
```

### <a name="bin"></a>bin
Тип данных: Object

Используется для упаковки DLL-файла. Вы можете сослаться на пакет, содержащий эту библиотеку DLL, и создать его. 

Содержит единственное свойство `assembly` типа String, значением которого является путь к сборке.   

Пример:

```json
"frameworks": {
    "netcoreapp1.0": {
        "bin": {
            "assembly": "c:/otherProject/otherdll.dll"
        }
    }
}
```

## <a name="runtimes"></a>runtimes
Тип данных: Object

Список [идентификаторов сред выполнения (RID)](../rid-catalog.md), поддерживаемых проектом (используется при публикации [автономных развертываний](../deploying/index.md#self-contained-deployments-scd)).

Пример:

```json
"runtimes": {
    "win7-x64": {},
    "win8-x64": {},
    "win81-x64": {},
    "win10-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
}
```

## <a name="usersecretsid"></a>userSecretsId
Тип данных: String

Указывает секретный идентификатор пользователя, который следует использовать во время разработки. Дополнительные сведения см. в разделе [Безопасное хранение секретов приложений во время разработки](https://docs.asp.net/en/latest/security/app-secrets.html).

Пример:

```json
{
    "userSecretsId": "aspnet-WebApp1-c23d27a4-eb88-4b18-9b77-2a93f3b15119"
}
```



<!--HONumber=Jan17_HO3-->


