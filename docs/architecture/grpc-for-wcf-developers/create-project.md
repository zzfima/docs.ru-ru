---
title: Создание нового ASP.NET Core проекта gRPC — gRPC для разработчиков WCF
description: Узнайте, как создать проект gRPC с помощью Visual Studio или командной строки.
ms.date: 09/02/2019
ms.openlocfilehash: ea6d7658404f61fedb25d7de7ddedb7c51437383
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711438"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="79432-103">Создание проекта ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="79432-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="79432-104">Пакет SDK для .NET Core поставляется с мощным средством CLI, `dotnet`, позволяющим создавать проекты и решения из командной строки и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="79432-104">The .NET Core SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="79432-105">Пакет SDK тесно интегрирован с Visual Studio, поэтому все доступно также через знакомый графический пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="79432-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="79432-106">В этой главе показаны оба способа создания нового проекта ASP.NET Core gRPC.</span><span class="sxs-lookup"><span data-stu-id="79432-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="79432-107">Создание проекта с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79432-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79432-108">Для разработки любого приложения ASP.NET Core 3,0 требуется Visual Studio 2019 16,3 или более поздней версии с установленной рабочей нагрузкой **ASP.NET и Web Development** .</span><span class="sxs-lookup"><span data-stu-id="79432-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="79432-109">Создайте пустое решение с именем **традерсис** из шаблона *пустого решения* .</span><span class="sxs-lookup"><span data-stu-id="79432-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="79432-110">Добавьте папку решения с именем `src`.</span><span class="sxs-lookup"><span data-stu-id="79432-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="79432-111">Затем щелкните правой кнопкой мыши папку и выберите **добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="79432-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="79432-112">Введите `grpc` в поле поиска шаблона, и вы увидите шаблон проекта с именем `gRPC Service`.</span><span class="sxs-lookup"><span data-stu-id="79432-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![Снимок экрана: диалоговое окно "Добавление нового проекта"](media/create-project/new-grpc-project.png)

<span data-ttu-id="79432-114">Нажмите кнопку **Далее** , чтобы перейти в диалоговое окно **Настройка нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="79432-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="79432-115">Присвойте проекту имя `TraderSys.Portfolios`и добавьте подкаталог `src` в **Расположение**.</span><span class="sxs-lookup"><span data-stu-id="79432-115">Name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Снимок экрана: диалоговое окно "Настройка нового проекта"](media/create-project/configure-project.png)

<span data-ttu-id="79432-117">Нажмите кнопку **Далее** , чтобы перейти к диалоговому окну **Создание новой службы gRPC** .</span><span class="sxs-lookup"><span data-stu-id="79432-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![Снимок экрана: диалоговое окно "Создание службы gRPC"](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="79432-119">В настоящее время у вас есть ограниченные параметры для создания службы.</span><span class="sxs-lookup"><span data-stu-id="79432-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="79432-120">DOCKER будет добавлен позднее, поэтому пока оставьте этот параметр невыбранным.</span><span class="sxs-lookup"><span data-stu-id="79432-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="79432-121">Просто выберите **создать**.</span><span class="sxs-lookup"><span data-stu-id="79432-121">Just select **Create**.</span></span> <span data-ttu-id="79432-122">Будет создан первый проект ASP.NET Core 3,0 gRPC и добавлен в решение.</span><span class="sxs-lookup"><span data-stu-id="79432-122">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="79432-123">Если вы не хотите узнать о работе с `dotnet CLI`, перейдите к разделу [Очистка кода примера](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="79432-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-core-cli"></a><span data-ttu-id="79432-124">Создайте проект с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="79432-124">Create the project by using the .NET Core CLI</span></span>

<span data-ttu-id="79432-125">В этом разделе рассматривается создание решений и проектов из командной строки.</span><span class="sxs-lookup"><span data-stu-id="79432-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="79432-126">Создайте решение, как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="79432-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="79432-127">Флаг `-o` (или `--output`) указывает выходной каталог, который создается в текущем каталоге, если он еще не существует.</span><span class="sxs-lookup"><span data-stu-id="79432-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="79432-128">Имя решения совпадает с именем каталога: `TraderSys.sln`.</span><span class="sxs-lookup"><span data-stu-id="79432-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="79432-129">Можно указать другое имя с помощью флага `-n` (или `--name`).</span><span class="sxs-lookup"><span data-stu-id="79432-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="79432-130">ASP.NET Core 3,0 поставляется с шаблоном CLI для gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="79432-130">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="79432-131">Создайте новый проект с помощью этого шаблона, поместив его в подкаталог `src`, как обычный для ASP.NET Core проектов.</span><span class="sxs-lookup"><span data-stu-id="79432-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="79432-132">Проект именуется после каталога (`TraderSys.Portfolios.csproj`), если не указано другое имя с флагом `-n`.</span><span class="sxs-lookup"><span data-stu-id="79432-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="79432-133">Наконец, добавьте проект в решение с помощью команды `dotnet sln`:</span><span class="sxs-lookup"><span data-stu-id="79432-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="79432-134">Поскольку конкретный каталог содержит только один файл `.csproj`, можно указать только каталог, чтобы сохранить ввод.</span><span class="sxs-lookup"><span data-stu-id="79432-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="79432-135">Теперь это решение можно открыть в Visual Studio 2019, Visual Studio Code или любом другом редакторе.</span><span class="sxs-lookup"><span data-stu-id="79432-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="79432-136">Очистка кода примера</span><span class="sxs-lookup"><span data-stu-id="79432-136">Clean up the example code</span></span>

<span data-ttu-id="79432-137">Теперь вы создали пример службы с помощью шаблона gRPC, который был рассмотрен ранее в книге.</span><span class="sxs-lookup"><span data-stu-id="79432-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="79432-138">Это не полезно в нашем контексте торговли, поэтому мы будем изменять вещи для нашего первого проекта.</span><span class="sxs-lookup"><span data-stu-id="79432-138">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="79432-139">Переименование и изменение файла имени</span><span class="sxs-lookup"><span data-stu-id="79432-139">Rename and edit the proto file</span></span>

<span data-ttu-id="79432-140">Переименуйте файл `Protos/greet.proto` в `Protos/portfolios.proto`и откройте его в редакторе.</span><span class="sxs-lookup"><span data-stu-id="79432-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="79432-141">Удалите все после строки `package`.</span><span class="sxs-lookup"><span data-stu-id="79432-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="79432-142">Затем измените имена `option csharp_namespace`, `package` и `service` и удалите службу `SayHello` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79432-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="79432-143">Теперь код выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="79432-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="79432-144">Шаблон не добавляет часть пространства имен `Protos` по умолчанию, но ее добавление упрощает создание классов, создаваемых gRPC, и собственных классов, четко разделенных в коде.</span><span class="sxs-lookup"><span data-stu-id="79432-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="79432-145">Если переименовать файл `greet.proto` в интегрированной среде разработки (IDE), например Visual Studio, ссылка на этот файл будет автоматически обновлена в файле `.csproj`.</span><span class="sxs-lookup"><span data-stu-id="79432-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="79432-146">Но в другом редакторе, например Visual Studio Code, эта ссылка не обновляется автоматически, поэтому необходимо изменить файл проекта вручную.</span><span class="sxs-lookup"><span data-stu-id="79432-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="79432-147">В целевом расположении сборки gRPC имеется элемент `Protobuf` Item, позволяющий указать, какие `.proto` файлы должны быть скомпилированы, и какая форма требуется для создания кода (то есть "сервер" или "клиент").</span><span class="sxs-lookup"><span data-stu-id="79432-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="79432-148">Переименование класса `GreeterService`</span><span class="sxs-lookup"><span data-stu-id="79432-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="79432-149">Класс `GreeterService` находится в папке `Services` и наследуется от `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="79432-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="79432-150">Переименуйте его в `PortfolioService`и измените базовый класс на `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="79432-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="79432-151">Удалите `override` методы.</span><span class="sxs-lookup"><span data-stu-id="79432-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="79432-152">Существует ссылка на класс `GreeterService` в методе `Configure` в классе `Startup`.</span><span class="sxs-lookup"><span data-stu-id="79432-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="79432-153">Если вы использовали рефакторинг для переименования класса, эта ссылка должна быть обновлена автоматически.</span><span class="sxs-lookup"><span data-stu-id="79432-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="79432-154">Однако, если это не так, необходимо изменить его вручную.</span><span class="sxs-lookup"><span data-stu-id="79432-154">However, if you didn't, you need to edit it manually.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="79432-155">В следующем разделе мы добавим функции к этой новой службе.</span><span class="sxs-lookup"><span data-stu-id="79432-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="79432-156">[Назад](migrate-wcf-to-grpc.md)
>[Вперед](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="79432-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
