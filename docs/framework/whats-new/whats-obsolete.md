---
title: Что устарело в библиотеке классов .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
ms.openlocfilehash: 4de441ff55c3728f43742d6e467deeb47f400507
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140598"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="287e4-102">Что устарело в библиотеке классов .NET Framework</span><span class="sxs-lookup"><span data-stu-id="287e4-102">What's obsolete in the .NET Framework class library</span></span>

<span data-ttu-id="287e4-103">Со временем в платформу .NET Framework вносятся изменения.</span><span class="sxs-lookup"><span data-stu-id="287e4-103">The .NET Framework changes over time.</span></span> <span data-ttu-id="287e4-104">В каждой новой версии добавляются новые типы и члены типов, предоставляющие новые функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="287e4-104">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="287e4-105">Существующие типы и их члены постепенно изменяются.</span><span class="sxs-lookup"><span data-stu-id="287e4-105">Existing types and their members also change over time.</span></span> <span data-ttu-id="287e4-106">Например, некоторые типы становятся менее важными из-за того, что поддерживаемая ими технология заменяется на другую технологию, а некоторые методы вытесняются новыми методами, которые более удобны в использовании или обладают большей функциональностью.</span><span class="sxs-lookup"><span data-stu-id="287e4-106">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are either more convenient or more full-featured.</span></span>

<span data-ttu-id="287e4-107">Платформа .NET Framework и среда CLR ориентированы на поддержку обратной совместимости (которая позволяет запускать приложения, разработанные в одной версии платформы .NET Framework, в более новой версии .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="287e4-107">The .NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of the .NET Framework to run on the next version of the .NET Framework).</span></span> <span data-ttu-id="287e4-108">Это затрудняет простое удаление типа или его члена.</span><span class="sxs-lookup"><span data-stu-id="287e4-108">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="287e4-109">Вместо этого платформа .NET Framework указывает, что отдельный тип или член типа больше не следует использовать, помечая его как устаревший или нерекомендуемый.</span><span class="sxs-lookup"><span data-stu-id="287e4-109">Instead, the .NET Framework indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="287e4-110">Для перевода типа или члена типа в разряд нерекомендуемых он помечается, чтобы разработчики знали об отказе от него и у них было время к этому подготовиться.</span><span class="sxs-lookup"><span data-stu-id="287e4-110">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="287e4-111">Однако существующий код, в котором используется этот тип или член, продолжает выполняться в новой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="287e4-111">However, existing code that uses the type or member continues to run in the new version of the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="287e4-112">Применительно к типам и членам платформы .NET Framework термины *устаревший* и *нерекомендуемый* имеют одинаковое значение.</span><span class="sxs-lookup"><span data-stu-id="287e4-112">The terms *obsolete* and *deprecated* have the same meaning when applied to the types and members of the .NET Framework.</span></span>

## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="287e4-113">Атрибут ObsoleteAttribute</span><span class="sxs-lookup"><span data-stu-id="287e4-113">The ObsoleteAttribute attribute</span></span>

<span data-ttu-id="287e4-114">Платформа .NET Framework указывает, что тип или член типа является устаревшим, помечая его с помощью атрибута <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="287e4-114">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="287e4-115">Применение этого атрибута к типу или члену указывает на то, что этот тип или член будет удален в одной из последующих версий платформы .NET Framework без нарушения работы скомпилированного кода, в котором он используется.</span><span class="sxs-lookup"><span data-stu-id="287e4-115">Applying the attribute to a type or member indicates that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>

<span data-ttu-id="287e4-116">Кроме обозначения устаревшего типа или члена типа, атрибут <xref:System.ObsoleteAttribute> определяет, как компилятор обрабатывает исходный код, содержащий такой тип или член.</span><span class="sxs-lookup"><span data-stu-id="287e4-116">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="287e4-117">Компилятор может компилировать код, выдавая предупреждение, или считать использование такого типа или члена ошибкой.</span><span class="sxs-lookup"><span data-stu-id="287e4-117">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="287e4-118">В первом случае код успешно компилируется, но выдается предупреждение о том, что тип или член является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="287e4-118">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="287e4-119">Во втором случае происходит сбой компиляции.</span><span class="sxs-lookup"><span data-stu-id="287e4-119">In the second case, compilation fails.</span></span>

<span data-ttu-id="287e4-120">Даже если во время компиляции вместо предупреждения происходит ошибка, атрибут <xref:System.ObsoleteAttribute> не влияет на поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="287e4-120">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="287e4-121">Таким образом, приложения, использующие тип или член, который был успешно скомпилирован, всегда выполняются успешно.</span><span class="sxs-lookup"><span data-stu-id="287e4-121">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="287e4-122">Сбой вызывает только повторная компиляция такого приложения.</span><span class="sxs-lookup"><span data-stu-id="287e4-122">Only the attempt to recompile an application that uses the type or member fails.</span></span>

## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="287e4-123">Способ обработки устаревших типов и членов</span><span class="sxs-lookup"><span data-stu-id="287e4-123">How to handle obsolete types and members</span></span>

<span data-ttu-id="287e4-124">При обновлении и повторной компиляции существующего кода использование типа или члена, вызывающего предупреждение компилятора, полностью приемлемо.</span><span class="sxs-lookup"><span data-stu-id="287e4-124">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="287e4-125">Однако следует просматривать предупреждение компилятора для того, чтобы определить, следует ли изменить код приложения.</span><span class="sxs-lookup"><span data-stu-id="287e4-125">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="287e4-126">Если в предупреждении не указан допустимый альтернативный вариант, следует выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="287e4-126">If the message does not point to a suitable alternative, you should do either of the following:</span></span>

- <span data-ttu-id="287e4-127">Измените код, удалив такой тип или член, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="287e4-127">Change your code by removing the use of the type or member, if possible.</span></span>

     <span data-ttu-id="287e4-128">-или-</span><span class="sxs-lookup"><span data-stu-id="287e4-128">-or-</span></span>

- <span data-ttu-id="287e4-129">Просмотрите документацию по данной технологии, чтобы определить, что делать с таким нерекомендуемым типом или членом.</span><span class="sxs-lookup"><span data-stu-id="287e4-129">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>

<span data-ttu-id="287e4-130">Можно не выполнять повторную компиляцию существующего кода в более новой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="287e4-130">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="287e4-131">Вместо этого можно указать версию .NET Framework, в которой запускается имеющийся скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="287e4-131">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="287e4-132">Предположим, что у вас есть приложение app1.exe, скомпилированное на платформе .NET Framework 3.5, но требуется его запуск на платформе .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="287e4-132">For example, suppose that you have an application named app1.exe that was compiled against the .NET Framework 3.5, but you want the application to run against the .NET Framework 4.5.</span></span> <span data-ttu-id="287e4-133">Для этого необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="287e4-133">This requires the following steps:</span></span>

1. <span data-ttu-id="287e4-134">Создайте файл конфигурации для основного исполняемого файла и назовите его *appName*.exe.config, где *appName* — это имя исполняемого файла приложения.</span><span class="sxs-lookup"><span data-stu-id="287e4-134">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="287e4-135">Для используемого в данном примере приложения app1.exe необходимо создать файл конфигурации app1.exe.config.</span><span class="sxs-lookup"><span data-stu-id="287e4-135">For the application named app1.exe in our example, you would create a configuration file named app1.exe.config.</span></span>

2. <span data-ttu-id="287e4-136">Добавьте в этот файл конфигурации следующее.</span><span class="sxs-lookup"><span data-stu-id="287e4-136">Add the following to the configuration file.</span></span>

    ```xml
    <configuration>
       <startup> 
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

<span data-ttu-id="287e4-137">В следующей таблице перечислены строковые значения, которые можно назначить атрибуту `version` для выбора конкретной целевой версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="287e4-137">The following table lists the string values that you can assign to the `version` attribute to target a specific version of the .NET Framework:</span></span>

|<span data-ttu-id="287e4-138">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="287e4-138">.NET Framework version</span></span>|<span data-ttu-id="287e4-139">`version` строковое значение</span><span class="sxs-lookup"><span data-stu-id="287e4-139">`version` string</span></span>|
|-|-|
|<span data-ttu-id="287e4-140">4.8</span><span class="sxs-lookup"><span data-stu-id="287e4-140">4.8</span></span>|<span data-ttu-id="287e4-141">v4.0</span><span class="sxs-lookup"><span data-stu-id="287e4-141">v4.0</span></span>|
|<span data-ttu-id="287e4-142">4.7 (включая 4.7.1 и 4.7.2)</span><span class="sxs-lookup"><span data-stu-id="287e4-142">4.7 (including 4.7.1 and 4.7.2)</span></span>|<span data-ttu-id="287e4-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="287e4-143">v4.0</span></span>|
|<span data-ttu-id="287e4-144">4.6 (включая 4.6.1 и 4.6.2)</span><span class="sxs-lookup"><span data-stu-id="287e4-144">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="287e4-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="287e4-145">v4.0</span></span>|
|<span data-ttu-id="287e4-146">4.5 (включая 4.5.1 и 4.5.2)</span><span class="sxs-lookup"><span data-stu-id="287e4-146">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="287e4-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="287e4-147">v4.0</span></span>|
|<span data-ttu-id="287e4-148">4</span><span class="sxs-lookup"><span data-stu-id="287e4-148">4</span></span>|<span data-ttu-id="287e4-149">v4.0</span><span class="sxs-lookup"><span data-stu-id="287e4-149">v4.0</span></span>|
|<span data-ttu-id="287e4-150">3.5</span><span class="sxs-lookup"><span data-stu-id="287e4-150">3.5</span></span>|<span data-ttu-id="287e4-151">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="287e4-151">v2.0.50727</span></span>|
|<span data-ttu-id="287e4-152">2.0</span><span class="sxs-lookup"><span data-stu-id="287e4-152">2.0</span></span>|<span data-ttu-id="287e4-153">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="287e4-153">v2.0.50727</span></span>|
|<span data-ttu-id="287e4-154">1.1</span><span class="sxs-lookup"><span data-stu-id="287e4-154">1.1</span></span>|<span data-ttu-id="287e4-155">v1.1.4322</span><span class="sxs-lookup"><span data-stu-id="287e4-155">v1.1.4322</span></span>|
|<span data-ttu-id="287e4-156">1.0</span><span class="sxs-lookup"><span data-stu-id="287e4-156">1.0</span></span>|<span data-ttu-id="287e4-157">v1.0.3705</span><span class="sxs-lookup"><span data-stu-id="287e4-157">v1.0.3705</span></span>|

## <a name="obsolete-lists-for-the-net-framework-45-and-later-versions"></a><span data-ttu-id="287e4-158">Списки устаревших элементов для .NET Framework 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="287e4-158">Obsolete lists for the .NET Framework 4.5 and later versions</span></span>

- [<span data-ttu-id="287e4-159">Устаревшие типы</span><span class="sxs-lookup"><span data-stu-id="287e4-159">Obsolete Types</span></span>](obsolete-types.md)
- [<span data-ttu-id="287e4-160">Устаревшие члены</span><span class="sxs-lookup"><span data-stu-id="287e4-160">Obsolete Members</span></span>](obsolete-members.md)

## <a name="obsolete-lists-for-previous-versions"></a><span data-ttu-id="287e4-161">Списки устаревших элементов для предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="287e4-161">Obsolete lists for previous versions</span></span>

- <span data-ttu-id="287e4-162">[Устаревшие типы в платформе .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="287e4-162">[Obsolete Types in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span></span>

- <span data-ttu-id="287e4-163">[Устаревшие члены в платформе .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="287e4-163">[Obsolete Members in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span></span>

- <span data-ttu-id="287e4-164">[Список устаревших элементов в платформе .NET Framework 3.5](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="287e4-164">[.NET Framework 3.5 Obsolete List](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span></span>

- <span data-ttu-id="287e4-165">[Список устаревших элементов в платформе .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="287e4-165">[.NET Framework 2.0 Obsolete List](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="287e4-166">См. также</span><span class="sxs-lookup"><span data-stu-id="287e4-166">See also</span></span>

- [<span data-ttu-id="287e4-167">\<Поддерживаемый элемент среды выполнения</span><span class="sxs-lookup"><span data-stu-id="287e4-167">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
