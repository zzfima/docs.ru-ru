---
title: "Отражение и машинный код .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e248071a0d35c5552976e5e4663094b76ee162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="reflection-and-net-native"></a><span data-ttu-id="67e0a-102">Отражение и машинный код .NET</span><span class="sxs-lookup"><span data-stu-id="67e0a-102">Reflection and .NET Native</span></span>
<span data-ttu-id="67e0a-103">В платформа.NET Framework управляемая разработка поддерживает метапрограммирование через интерфейс API отражения.</span><span class="sxs-lookup"><span data-stu-id="67e0a-103">In the .NET Framework, managed development supports metaprogramming through the reflection API.</span></span> <span data-ttu-id="67e0a-104">Отражение позволяет проверять объекты в приложении, вызывать методы для объектов, обнаруженные в результате проверки, создавать новые типы во время выполнения и поддерживает множество других сценариев динамического кода.</span><span class="sxs-lookup"><span data-stu-id="67e0a-104">Reflection allows you to inspect objects in an app, call methods on objects discovered through inspection, generate new types at run time, and supports many other dynamic code scenarios.</span></span> <span data-ttu-id="67e0a-105">Оно также поддерживает сериализацию и десериализацию, позволяющую сохранять значения полей объекта и восстанавливать их позже.</span><span class="sxs-lookup"><span data-stu-id="67e0a-105">It also supports serialization and deserialization, which allows an object's field values to be persisted and later restored.</span></span> <span data-ttu-id="67e0a-106">Все эти сценарии требуют использования JIT-компилятора платформы .NET Framework для генерации машинного кода на основе имеющихся метаданных.</span><span class="sxs-lookup"><span data-stu-id="67e0a-106">These scenarios all require the .NET Framework just-in-time (JIT) compiler to generate native code based on available metadata.</span></span>  
  
 <span data-ttu-id="67e0a-107">Среда выполнения [!INCLUDE[net_native](../../../includes/net-native-md.md)] не включает JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="67e0a-107">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime doesn't include a JIT compiler.</span></span> <span data-ttu-id="67e0a-108">В результате все необходимые машинные коды должны быть созданы заранее.</span><span class="sxs-lookup"><span data-stu-id="67e0a-108">As a result, all necessary native code must be generated in advance.</span></span> <span data-ttu-id="67e0a-109">Используется набор эвристических правил, чтобы определить, какой код должен создаваться, но они не могут охватывать все возможные сценарии метапрограммирования.</span><span class="sxs-lookup"><span data-stu-id="67e0a-109">A set of heuristics is used to determine what code should be generated, but these heuristics cannot cover all possible metaprogramming scenarios.</span></span>  <span data-ttu-id="67e0a-110">Таким образом, необходимо предоставить подсказки для этих сценариев метапрограммирования с помощью [директив среды выполнения](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="67e0a-110">Therefore, you must provide hints for these metaprogramming scenarios by using [runtime directives](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span> <span data-ttu-id="67e0a-111">Если необходимые метаданные или код реализации недоступны во время выполнения, приложение вызывает исключение [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) или [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="67e0a-111">If the necessary metadata or implementation code is not available at runtime, your app throws a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md), or [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) exception.</span></span> <span data-ttu-id="67e0a-112">Существуют два средства устранения неполадок, создающие соответствующую запись для файла директив среды выполнения, который устраняет исключение.</span><span class="sxs-lookup"><span data-stu-id="67e0a-112">Two troubleshooters are available that will generate the appropriate entry for your runtime directives file that eliminates the exception:</span></span>  
  
-   <span data-ttu-id="67e0a-113">[Средство устранения неполадок MissingMetadataException](http://dotnet.github.io/native/troubleshooter/type.html) для типов.</span><span class="sxs-lookup"><span data-stu-id="67e0a-113">The [MissingMetadataException troubleshooter](http://dotnet.github.io/native/troubleshooter/type.html) for types.</span></span>  
  
-   <span data-ttu-id="67e0a-114">[Средство устранения неполадок MissingMetadataException](http://dotnet.github.io/native/troubleshooter/method.html) для методов.</span><span class="sxs-lookup"><span data-stu-id="67e0a-114">The [MissingMetadataException troubleshooter](http://dotnet.github.io/native/troubleshooter/method.html) for methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67e0a-115">Общие сведения о процессе компиляции машинного кода .NET, обосновывающие необходимость файла директив среды выполнения, см. в разделе [Машинный код .NET и компиляция](../../../docs/framework/net-native/net-native-and-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="67e0a-115">For an overview of the .NET Native compilation process that provides background on why a runtime directives file is needed, see [.NET Native and Compilation](../../../docs/framework/net-native/net-native-and-compilation.md).</span></span>  
  
 <span data-ttu-id="67e0a-116">Кроме того [!INCLUDE[net_native](../../../includes/net-native-md.md)] не позволяет выполнить отражение через закрытые члены библиотеки классов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="67e0a-116">In addition, [!INCLUDE[net_native](../../../includes/net-native-md.md)] doesn't allow you to reflect over private members of the .NET Framework class library.</span></span> <span data-ttu-id="67e0a-117">Например, вызов свойства <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> для извлечения полей типа библиотеки классов платформы .NET Framework возвращает только открытые или защищенные поля.</span><span class="sxs-lookup"><span data-stu-id="67e0a-117">For example, a call to the <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> property to retrieve the fields of a .NET Framework class library type returns only public or protected fields.</span></span>  
  
 <span data-ttu-id="67e0a-118">В следующих разделах содержится основная и справочная документация, которая может потребоваться для поддержки отражения и сериализации в приложениях:</span><span class="sxs-lookup"><span data-stu-id="67e0a-118">The following topics provide the conceptual and reference documentation that you need to support reflection and serialization in your apps:</span></span>  
  
-   [<span data-ttu-id="67e0a-119">API-интерфейсы, основанные на отражении</span><span class="sxs-lookup"><span data-stu-id="67e0a-119">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
-   [<span data-ttu-id="67e0a-120">Справочник по API отражения</span><span class="sxs-lookup"><span data-stu-id="67e0a-120">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
-   [<span data-ttu-id="67e0a-121">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="67e0a-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="67e0a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="67e0a-122">See Also</span></span>  
 [<span data-ttu-id="67e0a-123">Компиляция приложений с помощью машинного кода .NET</span><span class="sxs-lookup"><span data-stu-id="67e0a-123">Compiling Apps with .NET Native</span></span>](../../../docs/framework/net-native/index.md)  
 [<span data-ttu-id="67e0a-124">.NET Native и компиляция</span><span class="sxs-lookup"><span data-stu-id="67e0a-124">.NET Native and Compilation</span></span>](../../../docs/framework/net-native/net-native-and-compilation.md)
