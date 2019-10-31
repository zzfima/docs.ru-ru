---
title: Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: aea88430d8f83234a1568bcaf433c2a75492e23a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195916"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="3255e-102">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="3255e-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="3255e-103">В этом разделе описываются интерфейсы, которые могут использоваться неуправляемыми узлами для интеграции среды CLR в .NET Framework 4, .NET Framework 4,5 и более поздних версий в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="3255e-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework 4, .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="3255e-104">Эти интерфейсы предоставляют основному приложению методы для настройки и загрузки среды выполнения в процесс.</span><span class="sxs-lookup"><span data-stu-id="3255e-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="3255e-105">Начиная с .NET Framework 4, все интерфейсы размещения имеют следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="3255e-105">Starting with the .NET Framework 4, all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="3255e-106">Они используют управление жизненным циклом (`AddRef` и `Release`), инкапсуляцию (неявный контекст) и `QueryInterface` из COM.</span><span class="sxs-lookup"><span data-stu-id="3255e-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="3255e-107">Они не используют типы COM, такие как `BSTR`, `SAFEARRAY`или `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="3255e-107">They do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="3255e-108">Нет моделей апартамента, агрегирования или активации реестра, использующих [функцию CoCreateInstance](https://go.microsoft.com/fwlink/?LinkId=142894).</span><span class="sxs-lookup"><span data-stu-id="3255e-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](https://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3255e-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="3255e-109">In This Section</span></span>  
 [<span data-ttu-id="3255e-110">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="3255e-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="3255e-111">Предоставляет методы для проверки использования памяти и ЦП домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3255e-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="3255e-112">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="3255e-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="3255e-113">Позволяет узлу указать Диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.</span><span class="sxs-lookup"><span data-stu-id="3255e-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="3255e-114">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="3255e-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="3255e-115">Предоставляет метод [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) , который позволяет основному приложению задать размер сегмента сборки мусора и максимальный размер поколения 0 в результате создания системы сборки мусора для значений, превышающих `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="3255e-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="3255e-116">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="3255e-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="3255e-117">Предоставляет методы, возвращающие определенную версию среды CLR, список всех установленных CLR, список всех выполняемых в процессе сред выполнения, возвращение интерфейса активации и обнаружение версии среды CLR, используемой для компиляции сборки.</span><span class="sxs-lookup"><span data-stu-id="3255e-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="3255e-118">Интерфейс ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="3255e-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="3255e-119">Предоставляет метод [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , ПРЕДОСТАВЛЯЮЩИЙ интерфейс CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3255e-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="3255e-120">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="3255e-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="3255e-121">Предоставляет методы, возвращающие сведения о конкретной среде выполнения, включая версию, каталог и состояние загрузки.</span><span class="sxs-lookup"><span data-stu-id="3255e-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="3255e-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3255e-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="3255e-123">Предоставляет базовые глобальные статические функции для подписи сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="3255e-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="3255e-124">Все методы [метод iclrstrongname](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) возвращают стандартные значения HRESULT для com.</span><span class="sxs-lookup"><span data-stu-id="3255e-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="3255e-125">Интерфейс ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="3255e-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="3255e-126">Предоставляет возможность создания строгих имен с помощью группы SHA-2 алгоритмов безопасных хэширования (SHA-256, SHA-384 и SHA-512).</span><span class="sxs-lookup"><span data-stu-id="3255e-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="3255e-127">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="3255e-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="3255e-128">Предоставляет все функциональные возможности [интерфейса ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); Кроме того, предоставляет методы, которые позволяют задерживать прерывания потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="3255e-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3255e-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3255e-129">Related Sections</span></span>  
 [<span data-ttu-id="3255e-130">Устаревшие интерфейсы размещения CLR и коклассы</span><span class="sxs-lookup"><span data-stu-id="3255e-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="3255e-131">Описание интерфейсов размещения, поставляемых с .NET Framework версиями 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="3255e-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="3255e-132">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="3255e-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="3255e-133">Описывает интерфейсы размещения, предоставляемые с .NET Framework версиями 2,0, 3,0 и 3,5.</span><span class="sxs-lookup"><span data-stu-id="3255e-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="3255e-134">Размещение</span><span class="sxs-lookup"><span data-stu-id="3255e-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="3255e-135">Введение в размещение в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3255e-135">Introduces hosting in the .NET Framework.</span></span>
