---
title: Выберите языковую версию Visual Basic
description: Настройте компилятор выполнять проверку синтаксиса, с помощью определенной версией компилятора.
ms.date: 05/24/2018
ms.openlocfilehash: 3b6d8055dbf64f2a5c38f46b6d66794fc48a1cea
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415108"
---
# <a name="select-the-visual-basic-language-version"></a><span data-ttu-id="93b9e-103">Выберите языковую версию Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93b9e-103">Select the Visual Basic language version</span></span>

<span data-ttu-id="93b9e-104">Компилятор Visual Basic по умолчанию последней основной версии языка, которая была освобождена.</span><span class="sxs-lookup"><span data-stu-id="93b9e-104">The Visual Basic compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="93b9e-105">Можно выбрать компиляцию любого проекта с помощью новой доработанной версии языка.</span><span class="sxs-lookup"><span data-stu-id="93b9e-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="93b9e-106">Выбор более новой версии языка позволяет использовать в проекте новейшие возможности языка.</span><span class="sxs-lookup"><span data-stu-id="93b9e-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="93b9e-107">В других случаях может потребоваться убедиться, что проект компилируется без ошибок при использовании более старой версии языка.</span><span class="sxs-lookup"><span data-stu-id="93b9e-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="93b9e-108">Эта возможность разделяет установку новых версий пакета SDK и средств в среде разработки и включение новых возможностей языка в проект.</span><span class="sxs-lookup"><span data-stu-id="93b9e-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="93b9e-109">Вы можете установить последнюю версию пакета SDK и средств на компьютер сборки.</span><span class="sxs-lookup"><span data-stu-id="93b9e-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="93b9e-110">В каждом проекте можно настроить использование определенной версии языка для сборки.</span><span class="sxs-lookup"><span data-stu-id="93b9e-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="93b9e-111">Существует три способа задать версию языка:</span><span class="sxs-lookup"><span data-stu-id="93b9e-111">There are three ways to set the language version:</span></span>

- <span data-ttu-id="93b9e-112">Вручную изменить ваш [ **.vbproj** файла](#edit-the-vbproj-file)</span><span class="sxs-lookup"><span data-stu-id="93b9e-112">Manually edit your [**.vbproj** file](#edit-the-vbproj-file)</span></span>
- <span data-ttu-id="93b9e-113">Задать версию языка [в подкаталог для нескольких проектов](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="93b9e-113">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects)</span></span>
- <span data-ttu-id="93b9e-114">Настройка [ `-langversion` параметр компилятора](#set-the-langversion-compiler-option)</span><span class="sxs-lookup"><span data-stu-id="93b9e-114">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option)</span></span>

## <a name="edit-the-vbproj-file"></a><span data-ttu-id="93b9e-115">Измените vbproj-файл</span><span class="sxs-lookup"><span data-stu-id="93b9e-115">Edit the vbproj file</span></span>

<span data-ttu-id="93b9e-116">Можно задать версию языка в вашей **.vbproj** файл.</span><span class="sxs-lookup"><span data-stu-id="93b9e-116">You can set the language version in your **.vbproj** file.</span></span> <span data-ttu-id="93b9e-117">Добавьте следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="93b9e-117">Add the following element:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="93b9e-118">Значение `latest` использует последний дополнительный номер версии языка Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="93b9e-118">The value `latest` uses the latest minor version of the Visual Basic language.</span></span> <span data-ttu-id="93b9e-119">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="93b9e-119">Valid values are:</span></span>

|<span data-ttu-id="93b9e-120">Значение</span><span class="sxs-lookup"><span data-stu-id="93b9e-120">Value</span></span>|<span data-ttu-id="93b9e-121">Значение</span><span class="sxs-lookup"><span data-stu-id="93b9e-121">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="93b9e-122">default</span><span class="sxs-lookup"><span data-stu-id="93b9e-122">default</span></span>|<span data-ttu-id="93b9e-123">Компилятор допускает использование любого допустимого синтаксиса языка из последней основной версии, которую он поддерживает.</span><span class="sxs-lookup"><span data-stu-id="93b9e-123">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="93b9e-124">9</span><span class="sxs-lookup"><span data-stu-id="93b9e-124">9</span></span>|<span data-ttu-id="93b9e-125">Компилятор принимает только синтаксис, включенные в Visual Basic 9.0 или более раннюю.</span><span class="sxs-lookup"><span data-stu-id="93b9e-125">The compiler accepts only syntax that is included in Visual Basic 9.0 or lower.</span></span>|
|<span data-ttu-id="93b9e-126">10</span><span class="sxs-lookup"><span data-stu-id="93b9e-126">10</span></span>|<span data-ttu-id="93b9e-127">Компилятор принимает только синтаксис, включенные в Visual Basic 10.0 или более раннюю.</span><span class="sxs-lookup"><span data-stu-id="93b9e-127">The compiler accepts only syntax that is included in Visual Basic 10.0 or lower.</span></span>|
|<span data-ttu-id="93b9e-128">11</span><span class="sxs-lookup"><span data-stu-id="93b9e-128">11</span></span>|<span data-ttu-id="93b9e-129">Компилятор принимает только синтаксис, включенные в Visual Basic 11.0 или более раннюю.</span><span class="sxs-lookup"><span data-stu-id="93b9e-129">The compiler accepts only syntax that is included in Visual Basic 11.0 or lower.</span></span>|
|<span data-ttu-id="93b9e-130">12</span><span class="sxs-lookup"><span data-stu-id="93b9e-130">12</span></span>|<span data-ttu-id="93b9e-131">Компилятор принимает только синтаксис, включенные в Visual Basic 12.0 или более раннюю.</span><span class="sxs-lookup"><span data-stu-id="93b9e-131">The compiler accepts only syntax that is included in Visual Basic 12.0 or lower.</span></span>|
|<span data-ttu-id="93b9e-132">14</span><span class="sxs-lookup"><span data-stu-id="93b9e-132">14</span></span>|<span data-ttu-id="93b9e-133">Компилятор принимает только синтаксис, включенные в Visual Basic 14.0 или ниже.</span><span class="sxs-lookup"><span data-stu-id="93b9e-133">The compiler accepts only syntax that is included in Visual Basic 14.0 or lower.</span></span>|
|<span data-ttu-id="93b9e-134">15</span><span class="sxs-lookup"><span data-stu-id="93b9e-134">15</span></span>|<span data-ttu-id="93b9e-135">Компилятор принимает только синтаксис, включенные в Visual Basic 15.0 или более раннюю.</span><span class="sxs-lookup"><span data-stu-id="93b9e-135">The compiler accepts only syntax that is included in Visual Basic 15.0 or lower.</span></span>|
|<span data-ttu-id="93b9e-136">15.3</span><span class="sxs-lookup"><span data-stu-id="93b9e-136">15.3</span></span>|<span data-ttu-id="93b9e-137">Компилятор принимает только синтаксис, включенные в Visual Basic 15.3 или более раннюю.</span><span class="sxs-lookup"><span data-stu-id="93b9e-137">The compiler accepts only syntax that is included in Visual Basic 15.3 or lower.</span></span>|
|<span data-ttu-id="93b9e-138">15.5</span><span class="sxs-lookup"><span data-stu-id="93b9e-138">15.5</span></span>|<span data-ttu-id="93b9e-139">Компилятор принимает только синтаксис, включенные в Visual Basic 15.5 или более раннюю.</span><span class="sxs-lookup"><span data-stu-id="93b9e-139">The compiler accepts only syntax that is included in Visual Basic 15.5 or lower.</span></span>|
|<span data-ttu-id="93b9e-140">latest</span><span class="sxs-lookup"><span data-stu-id="93b9e-140">latest</span></span>|<span data-ttu-id="93b9e-141">Компилятор допускает использование любого допустимого синтаксиса языка, который он может поддерживать.</span><span class="sxs-lookup"><span data-stu-id="93b9e-141">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="93b9e-142">В специальных строках `default` и `latest` будет указана соответственно последняя основная и дополнительная версия языка, установленная на компьютере сборки.</span><span class="sxs-lookup"><span data-stu-id="93b9e-142">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="93b9e-143">Настройка нескольких проектов</span><span class="sxs-lookup"><span data-stu-id="93b9e-143">Configure multiple projects</span></span>

<span data-ttu-id="93b9e-144">Можно создать файл **Directory.build.props**, содержащий элемент `<LangVersion>`, чтобы настроить несколько каталогов.</span><span class="sxs-lookup"><span data-stu-id="93b9e-144">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="93b9e-145">Обычно это делается в каталоге решения.</span><span class="sxs-lookup"><span data-stu-id="93b9e-145">You typically do that in your solution directory.</span></span> <span data-ttu-id="93b9e-146">Добавьте следующий код в файл **Directory.build.props** в каталоге решения:</span><span class="sxs-lookup"><span data-stu-id="93b9e-146">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="93b9e-147">Теперь сборок в каждый подкаталог каталога, содержащего этот файл будет использовать синтаксис Visual Basic версии 15.5.</span><span class="sxs-lookup"><span data-stu-id="93b9e-147">Now, builds in every subdirectory of the directory containing that file will use Visual Basic version 15.5 syntax.</span></span> <span data-ttu-id="93b9e-148">Дополнительные сведения см. в статье о [настройке сборки](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="93b9e-148">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="93b9e-149">Задание параметра компилятора langversion</span><span class="sxs-lookup"><span data-stu-id="93b9e-149">Set the langversion compiler option</span></span>

<span data-ttu-id="93b9e-150">Вы можете использовать параметр командной строки `-langversion`.</span><span class="sxs-lookup"><span data-stu-id="93b9e-150">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="93b9e-151">Дополнительные сведения см. в статье, посвященной параметру компилятора [-langversion](../reference/command-line-compiler/langversion.md).</span><span class="sxs-lookup"><span data-stu-id="93b9e-151">For more information, see the article on the [-langversion](../reference/command-line-compiler/langversion.md) compiler option.</span></span> <span data-ttu-id="93b9e-152">Вы можете просмотреть список допустимых значений, введя `vbc -langversion:?` .</span><span class="sxs-lookup"><span data-stu-id="93b9e-152">You can see a list of the valid values by typing  `vbc -langversion:?` .</span></span>
