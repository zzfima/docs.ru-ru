---
title: Предоставление доступа к компонентам .NET для COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: 09045fb455a2163641d6f4af0ba07520ead59f1e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123485"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="f7ac3-102">Предоставление доступа к компонентам .NET для COM</span><span class="sxs-lookup"><span data-stu-id="f7ac3-102">Exposing .NET components to COM</span></span>

<span data-ttu-id="f7ac3-103">Написание типа .NET и его использование из неуправляемого кода — это разные операции с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-103">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="f7ac3-104">В этом разделе приводятся советы по написанию управляемого кода, который взаимодействует с клиентами COM:</span><span class="sxs-lookup"><span data-stu-id="f7ac3-104">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="f7ac3-105">[Уточнение типов .NET для взаимодействия](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac3-105">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="f7ac3-106">Все управляемые типы, методы, свойства, поля и события, которые требуется предоставить модели COM, должны быть открытыми.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-106">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="f7ac3-107">Типы должны иметь открытый конструктор без параметров, который является единственным конструктором, доступным для вызова из модели COM.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-107">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="f7ac3-108">[Применение атрибутов взаимодействия](../../standard/native-interop/apply-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac3-108">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="f7ac3-109">С помощью настраиваемых атрибутов в управляемом коде можно расширять возможности взаимодействия для компонента.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-109">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="f7ac3-110">[Упаковка сборки для модели COM](packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac3-110">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="f7ac3-111">Разработчикам COM-приложений могут потребоваться общие сведения о шагах, которые необходимо выполнить для развертывания ваших сборок и использования ссылок на них.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-111">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="f7ac3-112">Кроме того, в этом разделе описываются задачи, связанные с использованием управляемого типа из клиента COM.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-112">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="f7ac3-113">Использование управляемого типа из модели COM</span><span class="sxs-lookup"><span data-stu-id="f7ac3-113">To consume a managed type from COM</span></span>

1. <span data-ttu-id="f7ac3-114">[Регистрация сборок в COM](registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac3-114">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="f7ac3-115">Типы в сборке и библиотеке типов необходимо регистрировать во время разработки.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-115">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="f7ac3-116">Если установщик не регистрирует сборку, необходимо предоставить разработчикам COM-приложений инструкции по использованию программы Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-116">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="f7ac3-117">[Создание ссылки на типы .NET из COM](how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac3-117">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="f7ac3-118">Разработчики COM-приложений могут использовать доступные средства и методы для ссылки на типы в сборке.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-118">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="f7ac3-119">[Вызов объекта .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f7ac3-119">[Call a .NET object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="f7ac3-120">Разработчики COM-приложений могут вызывать методы для объектов .NET так же, как и методы для любого неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-120">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="f7ac3-121">Например, API **CoCreateInstance** модели COM активирует объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-121">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="f7ac3-122">[Развертывание приложения для доступа к COM-приложению](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f7ac3-122">[Deploy an application for COM access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="f7ac3-123">Сборки со строгими именами могут устанавливаться в глобальный кэш сборок и должны быть подписаны их издателем.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-123">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="f7ac3-124">Сборки, которые не имеют строгих имен, должны устанавливаться в каталог приложения клиента.</span><span class="sxs-lookup"><span data-stu-id="f7ac3-124">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7ac3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f7ac3-125">See also</span></span>

- [<span data-ttu-id="f7ac3-126">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="f7ac3-126">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="f7ac3-127">Пример COM-взаимодействия. COM-клиент и сервер .NET</span><span class="sxs-lookup"><span data-stu-id="f7ac3-127">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)
