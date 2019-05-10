---
title: Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96bc833915dd74756220b5e79a2866b41389dd45
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630510"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="baef3-102">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="baef3-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="baef3-103">В этом разделе описываются интерфейсы, которые неуправляемые узлы могут использовать для интеграции общеязыковой среды выполнения (CLR) в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]и более поздних версий в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="baef3-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], and later versions into their applications.</span></span> <span data-ttu-id="baef3-104">Эти интерфейсы предоставляют методы для узла, для настройки и загрузки среды выполнения в процесс.</span><span class="sxs-lookup"><span data-stu-id="baef3-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="baef3-105">Начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], все размещения интерфейсы имеют следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="baef3-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="baef3-106">Они используют управление временем существования (`AddRef` и `Release`), инкапсуляцию (неявный контекст) и `QueryInterface` из COM.</span><span class="sxs-lookup"><span data-stu-id="baef3-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="baef3-107">Они не используют COM-типы например `BSTR`, `SAFEARRAY`, или `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="baef3-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="baef3-108">Отсутствуют модели подразделения, статистической обработки или активации реестра, используйте [функции CoCreateInstance](https://go.microsoft.com/fwlink/?LinkId=142894).</span><span class="sxs-lookup"><span data-stu-id="baef3-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](https://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="baef3-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="baef3-109">In This Section</span></span>  
 [<span data-ttu-id="baef3-110">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="baef3-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="baef3-111">Предоставляет методы, которые проверяют домен приложения использование памяти и ЦП.</span><span class="sxs-lookup"><span data-stu-id="baef3-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="baef3-112">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="baef3-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="baef3-113">Ведущее приложение может указать диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.</span><span class="sxs-lookup"><span data-stu-id="baef3-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="baef3-114">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="baef3-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="baef3-115">Предоставляет [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, который позволяет ведущему приложению задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0 значения больше `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="baef3-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="baef3-116">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="baef3-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="baef3-117">Предоставляет методы, возвращающие определенную версию среды CLR, перечислены все установленные среды CLR, все среды выполнения в процессе, возвращающие интерфейс активации и версию среды CLR, используемый для компиляции сборки.</span><span class="sxs-lookup"><span data-stu-id="baef3-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="baef3-118">Интерфейс ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="baef3-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="baef3-119">Предоставляет [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , предоставляющий интерфейс среды CLR на основании критериев политики, управляемой сборки, версии и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="baef3-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="baef3-120">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="baef3-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="baef3-121">Предоставляет методы, возвращающие сведения о конкретной среде выполнения, включая версию, каталог и состояние загрузки.</span><span class="sxs-lookup"><span data-stu-id="baef3-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="baef3-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="baef3-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="baef3-123">Предоставляет базовые глобальные статические функции для подписи сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="baef3-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="baef3-124">Все [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) методы возвращают стандартный COM HRESULT.</span><span class="sxs-lookup"><span data-stu-id="baef3-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="baef3-125">Интерфейс ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="baef3-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="baef3-126">Предоставляет возможность создания строгих имен, с помощью группы SHA-2 (SHA-256, SHA-384 и SHA-512) хэш-алгоритмов безопасности.</span><span class="sxs-lookup"><span data-stu-id="baef3-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="baef3-127">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="baef3-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="baef3-128">Предоставляет все функциональные возможности [интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); Кроме того, предоставляет методы, позволяющие прерывания потоков, задержки в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="baef3-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="baef3-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="baef3-129">Related Sections</span></span>  
 [<span data-ttu-id="baef3-130">Устаревшие интерфейсы размещения CLR и коклассы</span><span class="sxs-lookup"><span data-stu-id="baef3-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="baef3-131">Описание размещения интерфейсы, предоставляемые платформой .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="baef3-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="baef3-132">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="baef3-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="baef3-133">Описание размещения интерфейсы, предоставляемые платформой .NET Framework версии 2.0, 3.0 и 3.5.</span><span class="sxs-lookup"><span data-stu-id="baef3-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="baef3-134">Размещение</span><span class="sxs-lookup"><span data-stu-id="baef3-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="baef3-135">Представляет размещение в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="baef3-135">Introduces hosting in the .NET Framework.</span></span>
