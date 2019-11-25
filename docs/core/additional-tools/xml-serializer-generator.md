---
title: Генератор XML-сериализатора Майкрософт
description: Обзор генератора XML-сериализатора Майкрософт. Чтобы создать сборку сериализации XML для типов, содержащихся в проекте, используйте генератор XML-сериализатора.
author: mlacouture
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 403651978667c8cf531c3f87f1156f67206fb490
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522814"
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a>Использование генератора XML-сериализатора Майкрософт в .NET Core

Это руководство описывает использование генератора XML-сериализатора Майкрософт в приложении .NET Core на языке C#. В ходе работы с этим руководством вы:

> [!div class="checklist"]
>
> - как создать приложение .NET Core;
> - как добавить ссылку на пакет Microsoft.XmlSerializer.Generator;
> - как изменить MyApp.csproj для добавления зависимостей;
> - как добавить класс и XmlSerializer;
> - как собрать и запустить приложение.

Являясь аналогом [генератора XML-сериализатора (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) для .NET Framework, [пакет NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) предназначен для проектов .NET Core и .NET Standard. Он создает сборку сериализации XML для содержащихся в сборке типов, улучшая производительность при запуске сериализации или десериализации XML для объектов этих типов с помощью <xref:System.Xml.Serialization.XmlSerializer>.

## <a name="prerequisites"></a>Предварительные требования

Для работы с этим руководством вам понадобится следующее:

- [пакет SDK для .NET Core 2.1](https://dotnet.microsoft.com/download) или более поздней версии;
- любой редактор кода.

> [!TIP]
> Нужно ли устанавливать редактор кода? Попробуйте использовать [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a>Использование генератора XML-сериализатора Майкрософт в консольном приложении .NET Core

Приведенные ниже инструкции описывают, как использовать генератор XML-сериализатора Майкрософт в консольном приложении .NET Core.

### <a name="create-a-net-core-console-application"></a>Создание консольного приложения .NET Core

Откройте командную строку и создайте папку с именем *MyApp*. Перейдите в созданную папку и введите следующие команды:

```dotnetcli
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a>Добавление ссылки на пакет Microsoft.XmlSerializer.Generator в проекте MyApp

Используйте команду [`dotnet add package`](../tools//dotnet-add-package.md), чтобы добавить ссылку в проект.

Тип:

```dotnetcli
dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
```

### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a>Проверка изменений MyApp.csproj после добавления пакета

Для начала работы откройте текстовый редактор. Мы все еще работаем из каталога *MyApp*, где создали приложение.

Откройте *MyApp.csproj* в текстовом редакторе.

После запуска команды [`dotnet add package`](../tools//dotnet-add-package.md) в файл проекта *MyApp.csproj* добавляются следующие строки:

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a>Добавление другого раздела ItemGroup для поддержки инструмента CLI .NET Core

Добавьте следующие строки после рассмотренного нами раздела `ItemGroup`:

 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-a-class-in-the-application"></a>Добавление класса в приложении

Откройте *Program.cs* в текстовом редакторе. Добавьте в *Program.cs* класс *MyClass*.

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a>Создание `XmlSerializer` для MyClass

Добавьте следующую строку внутрь *Main*, чтобы создать `XmlSerializer` для MyClass:

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a>Построение и запуск приложения

Оставаясь в папке *MyApp*, запустите приложение с помощью [`dotnet run`](../tools/dotnet-run.md). При этом оно автоматически загружает и использует предварительно созданные сериализаторы во время выполнения.

Введите следующую команду в окне консоли:

```dotnetcli
dotnet run
```

> [!NOTE]
> [`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.

> [!IMPORTANT]
> Описанные в этом руководстве команды и шаги для запуска приложения используются только во время разработки. Когда вы будете готовы развернуть приложение, можете ознакомиться с другими [стратегиями развертывания](../deploying/index.md) для приложений .NET Core и командой [`dotnet publish`](../tools/dotnet-publish.md).

Если все пройдет успешно, в папке выходных данных создается сборка с именем *MyApp.XmlSerializers.dll*.

Поздравляем! Вы только что:
> [!div class="checklist"]
>
> - создали приложение .NET Core;
> - добавили ссылку на пакет Microsoft.XmlSerializer.Generator;
> - изменили MyApp.csproj для добавления зависимостей;
> - добавили класс и XmlSerializer;
> - выполнили сборку и запуск приложения.

## <a name="related-resources"></a>Связанные ресурсы

- [Введение в сериализацию XML](../../standard/serialization/introducing-xml-serialization.md)
- [Практическое руководство. Сериализация с использованием XmlSerializer (C#)](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
- [Практическое руководство. Serialize Using XmlSerializer (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md) (Сериализация с использованием XmlSerializer (Visual Basic))
