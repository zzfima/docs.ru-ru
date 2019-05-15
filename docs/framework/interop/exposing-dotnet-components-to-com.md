---
title: Предоставление COM-клиентам доступа к компонентам .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a6c2b755b87f6f01f08f54a2f2fc567868dbb55
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626346"
---
# <a name="exposing-net-framework-components-to-com"></a><span data-ttu-id="3190c-102">Предоставление COM-клиентам доступа к компонентам .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3190c-102">Exposing .NET Framework Components to COM</span></span>
<span data-ttu-id="3190c-103">Написание типа .NET и его использование из неуправляемого кода — это разные операции с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="3190c-103">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="3190c-104">В этом разделе приводятся советы по написанию управляемого кода, который взаимодействует с клиентами COM:</span><span class="sxs-lookup"><span data-stu-id="3190c-104">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>  
  
- <span data-ttu-id="3190c-105">[Уточнение типов .NET для взаимодействия](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="3190c-105">[Qualifying .NET types for interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).</span></span>  
  
     <span data-ttu-id="3190c-106">Все управляемые типы, методы, свойства, поля и события, которые требуется предоставить модели COM, должны быть открытыми.</span><span class="sxs-lookup"><span data-stu-id="3190c-106">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="3190c-107">Типы должны иметь открытый конструктор по умолчанию, который является единственным конструктором, доступным для вызова из модели COM.</span><span class="sxs-lookup"><span data-stu-id="3190c-107">Types must have a public default constructor, which is the only constructor that can be invoked through COM.</span></span>  
  
- <span data-ttu-id="3190c-108">[Применение атрибутов взаимодействия](../../../docs/framework/interop/applying-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="3190c-108">[Applying interop attributes](../../../docs/framework/interop/applying-interop-attributes.md).</span></span>  
  
     <span data-ttu-id="3190c-109">С помощью настраиваемых атрибутов в управляемом коде можно расширять возможности взаимодействия для компонента.</span><span class="sxs-lookup"><span data-stu-id="3190c-109">Custom attributes within managed code can enhance the interoperability of a component.</span></span>  
  
- <span data-ttu-id="3190c-110">[Упаковка сборки для модели COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="3190c-110">[Packaging an assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).</span></span>  
  
     <span data-ttu-id="3190c-111">Разработчикам COM-приложений могут потребоваться общие сведения о шагах, которые необходимо выполнить для развертывания ваших сборок и использования ссылок на них.</span><span class="sxs-lookup"><span data-stu-id="3190c-111">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>  
  
 <span data-ttu-id="3190c-112">Кроме того, в этом разделе описываются задачи, связанные с использованием управляемого типа из клиента COM.</span><span class="sxs-lookup"><span data-stu-id="3190c-112">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>  
  
#### <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="3190c-113">Использование управляемого типа из модели COM</span><span class="sxs-lookup"><span data-stu-id="3190c-113">To consume a managed type from COM</span></span>  
  
1. <span data-ttu-id="3190c-114">[Регистрация сборок в COM](../../../docs/framework/interop/registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="3190c-114">[Register assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md).</span></span>  
  
     <span data-ttu-id="3190c-115">Типы в сборке и библиотеке типов необходимо регистрировать во время разработки.</span><span class="sxs-lookup"><span data-stu-id="3190c-115">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="3190c-116">Если установщик не регистрирует сборку, необходимо предоставить разработчикам COM-приложений инструкции по использованию программы Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="3190c-116">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>  
  
2. <span data-ttu-id="3190c-117">[Создание ссылки на типы .NET из COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="3190c-117">[Reference .NET types from COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).</span></span>  
  
     <span data-ttu-id="3190c-118">Разработчики COM-приложений могут использовать доступные средства и методы для ссылки на типы в сборке.</span><span class="sxs-lookup"><span data-stu-id="3190c-118">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>  
  
3. <span data-ttu-id="3190c-119">[Вызов объекта .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3190c-119">[Call a .NET object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>  
  
     <span data-ttu-id="3190c-120">Разработчики COM-приложений могут вызывать методы для объектов .NET так же, как и методы для любого неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="3190c-120">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="3190c-121">Например, API **CoCreateInstance** модели COM активирует объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="3190c-121">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>  
  
4. <span data-ttu-id="3190c-122">[Развертывание приложения для доступа к COM-приложению](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3190c-122">[Deploy an application for COM access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>  
  
     <span data-ttu-id="3190c-123">Сборки со строгими именами могут устанавливаться в глобальный кэш сборок и должны быть подписаны их издателем.</span><span class="sxs-lookup"><span data-stu-id="3190c-123">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="3190c-124">Сборки, которые не имеют строгих имен, должны устанавливаться в каталог приложения клиента.</span><span class="sxs-lookup"><span data-stu-id="3190c-124">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3190c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3190c-125">See also</span></span>

- [<span data-ttu-id="3190c-126">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="3190c-126">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="3190c-127">Пример COM-взаимодействия. COM-клиент и сервер .NET</span><span class="sxs-lookup"><span data-stu-id="3190c-127">COM Interop Sample: COM Client and .NET Server</span></span>](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)
