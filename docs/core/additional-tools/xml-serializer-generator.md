---
title: "Использование генератора XML-сериализатора Майкрософт в .NET Core"
description: "Обзор генератора XML-сериализатора Майкрософт."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2017
ms.topic: tutorial
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: b2f52a068d128b2eb978c9e086508bd87e103ebc
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="b85eb-103">Использование генератора XML-сериализатора Майкрософт в .NET Core</span><span class="sxs-lookup"><span data-stu-id="b85eb-103">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="b85eb-104">Это руководство описывает использование генератора XML-сериализатора Майкрософт в приложении .NET Core на языке C#.</span><span class="sxs-lookup"><span data-stu-id="b85eb-104">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="b85eb-105">В ходе работы с этим руководством вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="b85eb-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="b85eb-106">как создать приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="b85eb-106">How to create a .NET Core app</span></span>
> * <span data-ttu-id="b85eb-107">как добавить ссылку на пакет Microsoft.XmlSerializer.Generator;</span><span class="sxs-lookup"><span data-stu-id="b85eb-107">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="b85eb-108">как изменить MyApp.csproj для добавления зависимостей;</span><span class="sxs-lookup"><span data-stu-id="b85eb-108">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="b85eb-109">как добавить класс и XmlSerializer;</span><span class="sxs-lookup"><span data-stu-id="b85eb-109">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="b85eb-110">как собрать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="b85eb-110">How to build and run the application</span></span> 

<span data-ttu-id="b85eb-111">Являясь аналогом [генератора XML-сериализатора (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) для .NET Framework, [пакет NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) предназначен для проектов .NET Core и .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="b85eb-111">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="b85eb-112">Он создает сборку сериализации XML для содержащихся в сборке типов, улучшая производительность при запуске сериализации или десериализации XML для объектов этих типов с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b85eb-112">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b85eb-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b85eb-113">Prerequisites</span></span>

<span data-ttu-id="b85eb-114">Для работы с этим руководством вам понадобится следующее:</span><span class="sxs-lookup"><span data-stu-id="b85eb-114">To complete this tutorial:</span></span>

* <span data-ttu-id="b85eb-115">Установите [пакет SDK для .NET Core 2.1.3 или более поздней версии](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="b85eb-115">Install [.NET Core SDK 2.1.3 or later](https://www.microsoft.com/net/download)</span></span>
* <span data-ttu-id="b85eb-116">Установите любой привычный для вас редактор кода, если еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="b85eb-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="b85eb-117">Нужно ли устанавливать редактор кода?</span><span class="sxs-lookup"><span data-stu-id="b85eb-117">Need to install a code editor?</span></span> <span data-ttu-id="b85eb-118">Попробуйте использовать [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="b85eb-118">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>
  
## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="b85eb-119">Использование генератора XML-сериализатора Майкрософт в консольном приложении .NET Core</span><span class="sxs-lookup"><span data-stu-id="b85eb-119">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span> 

<span data-ttu-id="b85eb-120">Приведенные ниже инструкции описывают, как использовать генератор XML-сериализатора Майкрософт в консольном приложении .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b85eb-120">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="b85eb-121">Создание консольного приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="b85eb-121">Create a .NET Core console application</span></span>

<span data-ttu-id="b85eb-122">Откройте командную строку и создайте папку с именем *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="b85eb-122">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="b85eb-123">Перейдите в созданную папку и введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="b85eb-123">Navigate to the folder you created and type the following command:</span></span>

```console
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="b85eb-124">Добавление ссылки на пакет Microsoft.XmlSerializer.Generator в проекте MyApp</span><span class="sxs-lookup"><span data-stu-id="b85eb-124">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="b85eb-125">Используйте команду [`dotnet add package`](../tools//dotnet-add-package.md), чтобы добавить ссылку в проект.</span><span class="sxs-lookup"><span data-stu-id="b85eb-125">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span> 

<span data-ttu-id="b85eb-126">Тип:</span><span class="sxs-lookup"><span data-stu-id="b85eb-126">Type:</span></span>
 
 ```console
 dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
 ```
 
### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="b85eb-127">Проверка изменений MyApp.csproj после добавления пакета</span><span class="sxs-lookup"><span data-stu-id="b85eb-127">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="b85eb-128">Для начала работы откройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="b85eb-128">Open your code editor and let's get started!</span></span> <span data-ttu-id="b85eb-129">Мы все еще работаем из каталога *MyApp*, где создали приложение.</span><span class="sxs-lookup"><span data-stu-id="b85eb-129">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="b85eb-130">Откройте *MyApp.csproj* в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="b85eb-130">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="b85eb-131">После запуска команды [`dotnet add package`](../tools//dotnet-add-package.md) в файл проекта *MyApp.csproj* добавляются следующие строки:</span><span class="sxs-lookup"><span data-stu-id="b85eb-131">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="b85eb-132">Добавление другого раздела ItemGroup для поддержки инструмента CLI .NET Core</span><span class="sxs-lookup"><span data-stu-id="b85eb-132">Add another ItemGroup section for .NET Core CLI Tool support</span></span>
 
 <span data-ttu-id="b85eb-133">Добавьте следующие строки после рассмотренного нами раздела `ItemGroup`:</span><span class="sxs-lookup"><span data-stu-id="b85eb-133">Add the following lines after the `ItemGroup` section that we inspected:</span></span>
 
 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-a-class-in-the-application"></a><span data-ttu-id="b85eb-134">Добавление класса в приложении</span><span class="sxs-lookup"><span data-stu-id="b85eb-134">Add a class in the application</span></span>

<span data-ttu-id="b85eb-135">Откройте *Program.cs* в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="b85eb-135">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="b85eb-136">Добавьте в *Program.cs* класс *MyClass*.</span><span class="sxs-lookup"><span data-stu-id="b85eb-136">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="b85eb-137">Создание `XmlSerializer` для MyClass</span><span class="sxs-lookup"><span data-stu-id="b85eb-137">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="b85eb-138">Добавьте следующую строку внутрь *Main*, чтобы создать `XmlSerializer` для MyClass:</span><span class="sxs-lookup"><span data-stu-id="b85eb-138">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="b85eb-139">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="b85eb-139">Build and run the application</span></span>

<span data-ttu-id="b85eb-140">Оставаясь в папке *MyApp*, запустите приложение с помощью [`dotnet run`](../tools/dotnet-run.md). При этом оно автоматически загружает и использует предварительно созданные сериализаторы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b85eb-140">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="b85eb-141">Введите следующую команду в окне консоли:</span><span class="sxs-lookup"><span data-stu-id="b85eb-141">Type the following command in your console window:</span></span>

 ```console
 $ dotnet run
 ```
> [!NOTE]
> <span data-ttu-id="b85eb-142">[`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для проверки того, выполнена ли сборка целевых объектов, а затем вызывает `dotnet <assembly.dll>` для запуска целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="b85eb-142">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b85eb-143">Описанные в этом руководстве команды и шаги для запуска приложения используются только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="b85eb-143">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="b85eb-144">Когда вы будете готовы развернуть приложение, можете ознакомиться с другими [стратегиями развертывания](../deploying/index.md) для приложений .NET Core и командой [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="b85eb-144">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="b85eb-145">Если все пройдет успешно, в папке выходных данных создается сборка с именем *MyApp.XmlSerializers.dll*.</span><span class="sxs-lookup"><span data-stu-id="b85eb-145">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span> 



<span data-ttu-id="b85eb-146">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="b85eb-146">Congratulations!</span></span> <span data-ttu-id="b85eb-147">Вы только что:</span><span class="sxs-lookup"><span data-stu-id="b85eb-147">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b85eb-148">создали приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="b85eb-148">Created a .NET Core app.</span></span>
> * <span data-ttu-id="b85eb-149">добавили ссылку на пакет Microsoft.XmlSerializer.Generator;</span><span class="sxs-lookup"><span data-stu-id="b85eb-149">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> * <span data-ttu-id="b85eb-150">изменили MyApp.csproj для добавления зависимостей;</span><span class="sxs-lookup"><span data-stu-id="b85eb-150">Edited your MyApp.csproj to add dependencies.</span></span>
> * <span data-ttu-id="b85eb-151">добавили класс и XmlSerializer;</span><span class="sxs-lookup"><span data-stu-id="b85eb-151">Added a class and an XmlSerializer.</span></span>
> * <span data-ttu-id="b85eb-152">выполнили сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="b85eb-152">Built and ran the application.</span></span> 

## <a name="related-resources"></a><span data-ttu-id="b85eb-153">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="b85eb-153">Related Resources</span></span>

* [<span data-ttu-id="b85eb-154">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="b85eb-154">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
* [<span data-ttu-id="b85eb-155">Практическое руководство. Сериализация с использованием XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="b85eb-155">How to: Serialize Using XmlSerializer (C#)</span></span>](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
* [<span data-ttu-id="b85eb-156">Практическое руководство. Сериализация с использованием XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b85eb-156">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
