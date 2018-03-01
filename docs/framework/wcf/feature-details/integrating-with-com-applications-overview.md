---
title: "Общие сведения об интеграции с приложениями COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b20ae5329f08e9391fd7b93218c44c3c1978a48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="93253-102">Общие сведения об интеграции с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="93253-102">Integrating with COM Applications Overview</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="93253-103"> предоставляет разработчику управляемого кода среду с широкими возможностями для создания подключаемых приложений.</span><span class="sxs-lookup"><span data-stu-id="93253-103"> provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="93253-104">Однако, если уже вложены существенные средства в неуправляемый код на основе модели COM и миграция нежелательна, веб-службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно интегрировать непосредственно в существующий код, используя моникер служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93253-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web services directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="93253-105">Моникер служб можно использовать в широком наборе сред разработки на базе модели COM, например в Office VBA, Visual Basic 6.0 и Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="93253-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93253-106">Для всех взаимодействий моникер служб использует коммуникационный канал [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93253-106">The service moniker uses a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] communication channel for all communication.</span></span> <span data-ttu-id="93253-107">Механизмы безопасности и идентификации для этого канала отличаются от механизмов, используемых в стандартных прокси-средствах COM и DCOM.</span><span class="sxs-lookup"><span data-stu-id="93253-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="93253-108">Кроме того, поскольку моникер служб использует коммуникационный канал [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], время ожидания по умолчанию составляет одну минуту для всех вызовов.</span><span class="sxs-lookup"><span data-stu-id="93253-108">In addition, because the service moniker uses a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] communication channel the default timeout period is one minute for all calls.</span></span>  
  
 <span data-ttu-id="93253-109">Моникер служб используется с функцией `GetObject`, чтобы для вызова веб-служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] разработчик неуправляемого кода мог воспользоваться строго типизированным подходом на основе модели COM.</span><span class="sxs-lookup"><span data-stu-id="93253-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web services.</span></span> <span data-ttu-id="93253-110">Для этого требуются локальное, видимое для модели COM определение контракта веб-службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и привязка, которая должна использоваться.</span><span class="sxs-lookup"><span data-stu-id="93253-110">This requires a local, COM-visible definition of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="93253-111">Подобно другим клиентам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], моникер служб должен создать типизированный канал к службе, хотя создание этого канала при первом вызове метода происходит прозрачно для COM-программиста.</span><span class="sxs-lookup"><span data-stu-id="93253-111">Like other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>  
  
 <span data-ttu-id="93253-112">Вместе с другими клиентами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании моникера приложения задают адрес, привязку и контракт для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="93253-112">In common with other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="93253-113">Контракт можно задать одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="93253-113">The contract can be specified in one of the following ways:</span></span>  
  
-   <span data-ttu-id="93253-114">Типизированный контракт: контракт регистрируется как видимый для модели COM тип на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="93253-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>  
  
-   <span data-ttu-id="93253-115">Контракт WSDL: контракт предоставляется в виде документа WSDL.</span><span class="sxs-lookup"><span data-stu-id="93253-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>  
  
-   <span data-ttu-id="93253-116">Контракт MEX: контракт получается в среде выполнения из конечной точки обмена метаданными (MEX).</span><span class="sxs-lookup"><span data-stu-id="93253-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="93253-117">Параметры, поддерживаемые моникером служб</span><span class="sxs-lookup"><span data-stu-id="93253-117">Parameters Supported by the Service Moniker</span></span>  
 <span data-ttu-id="93253-118">В следующей таблице представлены параметры, поддерживаемые моникером служб.</span><span class="sxs-lookup"><span data-stu-id="93253-118">The following table shows the parameters that are supported by the service moniker.</span></span>  
  
|<span data-ttu-id="93253-119">Параметр</span><span class="sxs-lookup"><span data-stu-id="93253-119">Parameter</span></span>|<span data-ttu-id="93253-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="93253-120">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="93253-121">URL-адрес службы.</span><span class="sxs-lookup"><span data-stu-id="93253-121">URL location of the service.</span></span>|  
|`binding`|<span data-ttu-id="93253-122">Имя раздела привязки из конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="93253-122">Binding section name from the application configuration.</span></span>|  
|`bindingConfiguration`|<span data-ttu-id="93253-123">Именованный экземпляр привязки из именованного раздела привязки.</span><span class="sxs-lookup"><span data-stu-id="93253-123">Named binding instance from within the named binding section.</span></span>|  
|`contract`|<span data-ttu-id="93253-124">Идентификатор интерфейса (IID), представляющий контракт службы или имя контракта (из MEX).</span><span class="sxs-lookup"><span data-stu-id="93253-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|  
|`wsdl`|<span data-ttu-id="93253-125">Документ WSDL, обеспечивающий альтернативную форму определения контракта.</span><span class="sxs-lookup"><span data-stu-id="93253-125">WSDL document that provides an alternative form of contract definition.</span></span>|  
|`spnIdentity`|<span data-ttu-id="93253-126">Идентификатор имени участника на уровне сервера (SPN), который должен использоваться для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="93253-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|  
|`upnIdentity`|<span data-ttu-id="93253-127">Идентификатор имени участника-пользователя (UPN), который должен использоваться для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="93253-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|  
|`dnsIdentity`|<span data-ttu-id="93253-128">Идентификатор DNS, который должен использоваться для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="93253-128">DNS identity to be used to communicate with the service.</span></span>|  
|`mexAddress`|<span data-ttu-id="93253-129">URL-адрес конечной точки службы для обмена метаданными (MEX).</span><span class="sxs-lookup"><span data-stu-id="93253-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|  
|`mexBinding`|<span data-ttu-id="93253-130">Имя раздела привязки из конфигурации приложения для соединения с конечной точкой MEX.</span><span class="sxs-lookup"><span data-stu-id="93253-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|  
|`mexBindingConfiguration`|<span data-ttu-id="93253-131">Именованный экземпляр привязки из именованного раздела привязки для соединения с конечной точкой MEX.</span><span class="sxs-lookup"><span data-stu-id="93253-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|  
|`bindingNamespace`|<span data-ttu-id="93253-132">Пространство имен для имени раздела привязки, полученное в результате MEX.</span><span class="sxs-lookup"><span data-stu-id="93253-132">Namespace of the binding section name from the retrieved MEX.</span></span>|  
|`contractNamespace`|<span data-ttu-id="93253-133">Пространство имен контракта, полученное в результате MEX.</span><span class="sxs-lookup"><span data-stu-id="93253-133">Namespace of the contract from the retrieved MEX.</span></span>|  
|`mexSpnIdentity`|<span data-ttu-id="93253-134">Идентификатор имени участника на уровне сервера (SPN), который должен использоваться для взаимодействия с конечной точкой MEX.</span><span class="sxs-lookup"><span data-stu-id="93253-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexUpnIdentity`|<span data-ttu-id="93253-135">Идентификатор имени участника-пользователя (UPN), который должен использоваться для взаимодействия с конечной точкой MEX.</span><span class="sxs-lookup"><span data-stu-id="93253-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexDnsIdentity`|<span data-ttu-id="93253-136">Идентификатор DNS, который должен использоваться для взаимодействия с конечной точкой MEX.</span><span class="sxs-lookup"><span data-stu-id="93253-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|  
|`serializer`|<span data-ttu-id="93253-137">Позволяет задать использование сериализатора "xml" или "datacontract".</span><span class="sxs-lookup"><span data-stu-id="93253-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="93253-138">Даже при использовании с клиентами, полностью основанными на модели COM, для моникера служб требуется [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], и на клиентском компьютере должна быть установлена платформа .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="93253-138">Even when used with entirely COM-based clients, the service moniker requires [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="93253-139">Также важно, чтобы в клиентские приложения, использующие моникер служб, была загружена соответствующая версия среды выполнения платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93253-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="93253-140">При использовании моникера в приложениях Office может потребоваться файл конфигурации, чтобы обеспечить загрузку надлежащей версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93253-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="93253-141">Например, при использовании Excel файл Excel.exe.config, расположенный в том же каталоге, что и файл Excel.exe, должен содержать следующий текст:</span><span class="sxs-lookup"><span data-stu-id="93253-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  <span data-ttu-id="93253-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="93253-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a><span data-ttu-id="93253-143">См. также</span><span class="sxs-lookup"><span data-stu-id="93253-143">See Also</span></span>  
 [<span data-ttu-id="93253-144">Практическое руководство. Регистрация и настройка моникера службы</span><span class="sxs-lookup"><span data-stu-id="93253-144">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
