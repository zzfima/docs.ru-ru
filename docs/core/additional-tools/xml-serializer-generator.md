---
title: Генератор XML-сериализатора Майкрософт
description: Обзор генератора XML-сериализатора Майкрософт. Чтобы создать сборку сериализации XML для типов, содержащихся в проекте, используйте генератор XML-сериализатора.
author: mlacouture
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 094dd1227033e167050ad73121b3005a592a0ae4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714527"
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="789c4-104">Использование генератора XML-сериализатора Майкрософт в .NET Core</span><span class="sxs-lookup"><span data-stu-id="789c4-104">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="789c4-105">Это руководство описывает использование генератора XML-сериализатора Майкрософт в приложении .NET Core на языке C#.</span><span class="sxs-lookup"><span data-stu-id="789c4-105">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="789c4-106">В ходе работы с этим руководством вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="789c4-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="789c4-107">как создать приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="789c4-107">How to create a .NET Core app</span></span>
> - <span data-ttu-id="789c4-108">как добавить ссылку на пакет Microsoft.XmlSerializer.Generator;</span><span class="sxs-lookup"><span data-stu-id="789c4-108">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="789c4-109">как изменить MyApp.csproj для добавления зависимостей;</span><span class="sxs-lookup"><span data-stu-id="789c4-109">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="789c4-110">как добавить класс и XmlSerializer;</span><span class="sxs-lookup"><span data-stu-id="789c4-110">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="789c4-111">как собрать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="789c4-111">How to build and run the application</span></span>

<span data-ttu-id="789c4-112">Являясь аналогом [генератора XML-сериализатора (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) для .NET Framework, [пакет NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) предназначен для проектов .NET Core и .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="789c4-112">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="789c4-113">Он создает сборку сериализации XML для содержащихся в сборке типов, улучшая производительность при запуске сериализации или десериализации XML для объектов этих типов с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="789c4-113">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="789c4-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="789c4-114">Prerequisites</span></span>

<span data-ttu-id="789c4-115">Для работы с этим руководством:</span><span class="sxs-lookup"><span data-stu-id="789c4-115">To complete this tutorial:</span></span>

- <span data-ttu-id="789c4-116">[пакет SDK для .NET Core 2.1](https://dotnet.microsoft.com/download) или более поздней версии;</span><span class="sxs-lookup"><span data-stu-id="789c4-116">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later.</span></span>
- <span data-ttu-id="789c4-117">любой редактор кода.</span><span class="sxs-lookup"><span data-stu-id="789c4-117">Your favorite code editor.</span></span>

> [!TIP]
> <span data-ttu-id="789c4-118">Нужно ли устанавливать редактор кода?</span><span class="sxs-lookup"><span data-stu-id="789c4-118">Need to install a code editor?</span></span> <span data-ttu-id="789c4-119">Попробуйте использовать [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="789c4-119">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>

## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="789c4-120">Использование генератора XML-сериализатора Майкрософт в консольном приложении .NET Core</span><span class="sxs-lookup"><span data-stu-id="789c4-120">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span>

<span data-ttu-id="789c4-121">Приведенные ниже инструкции описывают, как использовать генератор XML-сериализатора Майкрософт в консольном приложении .NET Core.</span><span class="sxs-lookup"><span data-stu-id="789c4-121">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="789c4-122">Создание консольного приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="789c4-122">Create a .NET Core console application</span></span>

<span data-ttu-id="789c4-123">Откройте командную строку и создайте папку с именем *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="789c4-123">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="789c4-124">Перейдите в созданную папку и введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="789c4-124">Navigate to the folder you created and type the following command:</span></span>

```dotnetcli
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="789c4-125">Добавление ссылки на пакет Microsoft.XmlSerializer.Generator в проекте MyApp</span><span class="sxs-lookup"><span data-stu-id="789c4-125">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="789c4-126">Используйте команду [`dotnet add package`](../tools//dotnet-add-package.md), чтобы добавить ссылку в проект.</span><span class="sxs-lookup"><span data-stu-id="789c4-126">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span>

<span data-ttu-id="789c4-127">Тип:</span><span class="sxs-lookup"><span data-stu-id="789c4-127">Type:</span></span>

```dotnetcli
dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
```

### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="789c4-128">Проверка изменений MyApp.csproj после добавления пакета</span><span class="sxs-lookup"><span data-stu-id="789c4-128">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="789c4-129">Для начала работы откройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="789c4-129">Open your code editor and let's get started!</span></span> <span data-ttu-id="789c4-130">Мы все еще работаем из каталога *MyApp*, где создали приложение.</span><span class="sxs-lookup"><span data-stu-id="789c4-130">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="789c4-131">Откройте *MyApp.csproj* в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="789c4-131">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="789c4-132">После запуска команды [`dotnet add package`](../tools//dotnet-add-package.md) в файл проекта *MyApp.csproj* добавляются следующие строки:</span><span class="sxs-lookup"><span data-stu-id="789c4-132">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="789c4-133">Добавление другого раздела ItemGroup для поддержки инструмента CLI .NET Core</span><span class="sxs-lookup"><span data-stu-id="789c4-133">Add another ItemGroup section for .NET Core CLI Tool support</span></span>

<span data-ttu-id="789c4-134">Добавьте следующие строки после рассмотренного нами раздела `ItemGroup`:</span><span class="sxs-lookup"><span data-stu-id="789c4-134">Add the following lines after the `ItemGroup` section that we inspected:</span></span>

 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-a-class-in-the-application"></a><span data-ttu-id="789c4-135">Добавление класса в приложении</span><span class="sxs-lookup"><span data-stu-id="789c4-135">Add a class in the application</span></span>

<span data-ttu-id="789c4-136">Откройте *Program.cs* в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="789c4-136">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="789c4-137">Добавьте в *Program.cs* класс *MyClass*.</span><span class="sxs-lookup"><span data-stu-id="789c4-137">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="789c4-138">Создание `XmlSerializer` для MyClass</span><span class="sxs-lookup"><span data-stu-id="789c4-138">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="789c4-139">Добавьте следующую строку внутрь *Main*, чтобы создать `XmlSerializer` для MyClass:</span><span class="sxs-lookup"><span data-stu-id="789c4-139">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="789c4-140">Создание и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="789c4-140">Build and run the application</span></span>

<span data-ttu-id="789c4-141">Оставаясь в папке *MyApp*, запустите приложение с помощью [`dotnet run`](../tools/dotnet-run.md). При этом оно автоматически загружает и использует предварительно созданные сериализаторы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="789c4-141">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="789c4-142">Введите следующую команду в окне консоли:</span><span class="sxs-lookup"><span data-stu-id="789c4-142">Type the following command in your console window:</span></span>

```dotnetcli
dotnet run
```

> [!NOTE]
> <span data-ttu-id="789c4-143">[`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="789c4-143">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="789c4-144">Описанные в этом руководстве команды и шаги для запуска приложения используются только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="789c4-144">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="789c4-145">Когда вы будете готовы развернуть приложение, можете ознакомиться с другими [стратегиями развертывания](../deploying/index.md) для приложений .NET Core и командой [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="789c4-145">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="789c4-146">Если все пройдет успешно, в папке выходных данных создается сборка с именем *MyApp.XmlSerializers.dll*.</span><span class="sxs-lookup"><span data-stu-id="789c4-146">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span>

<span data-ttu-id="789c4-147">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="789c4-147">Congratulations!</span></span> <span data-ttu-id="789c4-148">Вы только что:</span><span class="sxs-lookup"><span data-stu-id="789c4-148">You have just:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="789c4-149">создали приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="789c4-149">Created a .NET Core app.</span></span>
> - <span data-ttu-id="789c4-150">добавили ссылку на пакет Microsoft.XmlSerializer.Generator;</span><span class="sxs-lookup"><span data-stu-id="789c4-150">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> - <span data-ttu-id="789c4-151">изменили MyApp.csproj для добавления зависимостей;</span><span class="sxs-lookup"><span data-stu-id="789c4-151">Edited your MyApp.csproj to add dependencies.</span></span>
> - <span data-ttu-id="789c4-152">добавили класс и XmlSerializer;</span><span class="sxs-lookup"><span data-stu-id="789c4-152">Added a class and an XmlSerializer.</span></span>
> - <span data-ttu-id="789c4-153">выполнили сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="789c4-153">Built and ran the application.</span></span>

## <a name="related-resources"></a><span data-ttu-id="789c4-154">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="789c4-154">Related resources</span></span>

- [<span data-ttu-id="789c4-155">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="789c4-155">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="789c4-156">Сериализация с использованием XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="789c4-156">How to serialize using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
- [<span data-ttu-id="789c4-157">Практическое руководство. Сериализация с использованием XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="789c4-157">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
