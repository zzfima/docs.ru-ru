---
title: Предоставление клиентам .NET Framework доступа к COM-компонентам
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6987dea6f122819b9f1c0d334440d87545368942
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220116"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="d7dc1-102">Предоставление клиентам .NET Framework доступа к COM-компонентам</span><span class="sxs-lookup"><span data-stu-id="d7dc1-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="d7dc1-103">В этом разделе описывается процесс, в рамках которого существующий COM-компонент предоставляется управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="d7dc1-104">Сведения о разработке COM-серверов, которые тесно интегрируются с платформой .NET Framework, см. в разделе [Вопросы разработки для взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d7dc1-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="d7dc1-105">Существующие COM-компоненты являются ценными ресурсами для управляемого кода, выступая в качестве бизнес-приложений среднего уровня или изолированных функций.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="d7dc1-106">В идеале компонент содержит основную сборку взаимодействия и строго соответствует стандартам программирования модели COM.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="d7dc1-107">Предоставление клиентам .NET Framework доступа к COM-компонентам</span><span class="sxs-lookup"><span data-stu-id="d7dc1-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="d7dc1-108">[Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc1-108">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="d7dc1-109">Общеязыковая среда выполнения требует наличия метаданных для всех типов, включая COM-типы.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="d7dc1-110">Получить сборку, содержащую импортированные COM-типы, в виде метаданных можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="d7dc1-111">[Использование типов COM в управляемом коде](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d7dc1-111">[Use COM types in managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="d7dc1-112">Вы можете проверять COM-типы, активировать экземпляры и вызывать методы COM-объекта так же, как и для любого другого управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="d7dc1-113">[Компиляция проекта, использующего взаимодействие](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc1-113">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="d7dc1-114">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] предоставляет компиляторы для нескольких языков, соответствующих требованиям спецификации общеязыковой среды выполнения (CLS), включая [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# и C++.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="d7dc1-115">[Развертывание приложения взаимодействия](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc1-115">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="d7dc1-116">Приложения взаимодействия рекомендуется развертывать в виде подписанных сборок со [строгими именами](../app-domains/strong-named-assemblies.md) в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="d7dc1-116">Interop applications are best deployed as [strong-named](../app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dc1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d7dc1-117">See also</span></span>
- [<span data-ttu-id="d7dc1-118">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="d7dc1-118">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="d7dc1-119">[Вопросы разработки для взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d7dc1-119">[Design Considerations for Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="d7dc1-120">Пример COM-взаимодействия. Клиент .NET и COM-сервер</span><span class="sxs-lookup"><span data-stu-id="d7dc1-120">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="d7dc1-121">Независимость от языка и независимые от языка компоненты</span><span class="sxs-lookup"><span data-stu-id="d7dc1-121">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="d7dc1-122">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="d7dc1-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
