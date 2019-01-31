---
title: Примеры - WCF служб
ms.date: 03/30/2017
ms.assetid: 462a2218-f8c6-4fb7-95bc-64765459c429
ms.openlocfilehash: 3fbca09a7b50a15299cb8e805ac84c60e4b78fa7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268747"
---
# <a name="services"></a><span data-ttu-id="fa307-102">Службы</span><span class="sxs-lookup"><span data-stu-id="fa307-102">Services</span></span>

<span data-ttu-id="fa307-103">Этот раздел содержит образцы, демонстрирующие службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fa307-103">This section contains samples that demonstrate Windows Communication Foundation (WCF) services.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fa307-104">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="fa307-104">In this section</span></span>

- <span data-ttu-id="fa307-105">[Размещение](../../../../docs/framework/wcf/feature-details/hosting.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-105">[Hosting](../../../../docs/framework/wcf/feature-details/hosting.md)\\</span></span>
<span data-ttu-id="fa307-106">Демонстрирует размещение служб WCF.</span><span class="sxs-lookup"><span data-stu-id="fa307-106">Demonstrates hosting WCF services.</span></span>

- <span data-ttu-id="fa307-107">[Взаимодействие со службой](service-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-107">[Service Interoperability](service-interoperability.md)\\</span></span>
<span data-ttu-id="fa307-108">Показывает взаимодействие между WCF и другими технологиями служб.</span><span class="sxs-lookup"><span data-stu-id="fa307-108">Demonstrates interaction between WCF and other service technologies.</span></span>

- <span data-ttu-id="fa307-109">[Поведения](behaviors.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-109">[Behaviors](behaviors.md)\\</span></span>
<span data-ttu-id="fa307-110">Демонстрирует поведение службы WCF.</span><span class="sxs-lookup"><span data-stu-id="fa307-110">Demonstrates WCF service behaviors.</span></span>

- <span data-ttu-id="fa307-111">[Безопасность службы](service-security.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-111">[Service Security](service-security.md)\\</span></span>
<span data-ttu-id="fa307-112">Демонстрирует безопасность службы WCF.</span><span class="sxs-lookup"><span data-stu-id="fa307-112">Demonstrates WCF service security.</span></span>

- <span data-ttu-id="fa307-113">[Упрощенная конфигурация служб WCF](simplified-configuration-for-wcf-services.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-113">[Simplified Configuration for WCF Services](simplified-configuration-for-wcf-services.md)\\</span></span>
<span data-ttu-id="fa307-114">Показано, как реализовать и настроить типизированные службы и клиента с помощью WCF.</span><span class="sxs-lookup"><span data-stu-id="fa307-114">Demonstrates how to implement and configure a typical service and client using WCF.</span></span>

- <span data-ttu-id="fa307-115">[Использование стандартных конечных точек](usage-of-standard-endpoints.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-115">[Usage of Standard Endoints](usage-of-standard-endpoints.md)\\</span></span>
<span data-ttu-id="fa307-116">Демонстрирует использование стандартных конечных точек в файлах конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="fa307-116">Demonstrates how to use standard endpoints in service configuration files.</span></span>

- <span data-ttu-id="fa307-117">[Расширенная политика защиты](extended-protection-policy.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-117">[Extended Protection Policy](extended-protection-policy.md)\\</span></span>
<span data-ttu-id="fa307-118">Демонстрирует расширенную защиту, защитную инициативу, направленную на отражение атак типа «злоумышленник в середине».</span><span class="sxs-lookup"><span data-stu-id="fa307-118">Demonstrates Extended Protection, a security initiative for protecting against man-in-the-middle (MITM) attacks.</span></span>

- <span data-ttu-id="fa307-119">[Производство канала настройки](configuration-channel-factory.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-119">[Configuration Channel Factory](configuration-channel-factory.md)\\</span></span>
<span data-ttu-id="fa307-120">Демонстрирует использование действия класса <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="fa307-120">Demonstrates the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span>

- <span data-ttu-id="fa307-121">[Адресация](addressing.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-121">[Addressing](addressing.md)\\</span></span>
<span data-ttu-id="fa307-122">Показаны различные аспекты и возможности адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="fa307-122">Demonstrates various aspects and features of endpoint addresses.</span></span>

- <span data-ttu-id="fa307-123">[Императивные](imperative.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-123">[Imperative](imperative.md)\\</span></span>
<span data-ttu-id="fa307-124">Показывает, как определить привязку <xref:System.ServiceModel.WSHttpBinding> для службы в коде, вместо того чтобы определять привязку `wsHttpBinding` в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa307-124">Demonstrates how to define a <xref:System.ServiceModel.WSHttpBinding> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span>

- <span data-ttu-id="fa307-125">[Несколько контрактов](multiple-contracts.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-125">[Multiple Contracts](multiple-contracts.md)\\</span></span>
<span data-ttu-id="fa307-126">Демонстрируется способ реализации нескольких контрактов в службе и способ настройки конечных точек для взаимодействия с каждым из реализованных контрактов.</span><span class="sxs-lookup"><span data-stu-id="fa307-126">Demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span>

- <span data-ttu-id="fa307-127">[Несколько конечных точек](multiple-endpoints.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-127">[Multiple Endpoints](multiple-endpoints.md)\\</span></span>
<span data-ttu-id="fa307-128">Показано, как настроить несколько конечных точек на службе и как взаимодействовать с каждой конечной точкой со стороны клиента.</span><span class="sxs-lookup"><span data-stu-id="fa307-128">Demonstrates how to configure multiple endpoints on a service and how to communicate with each endpoint from a client.</span></span>

- <span data-ttu-id="fa307-129">[Несколько конечных точек по одному ListenUri](multiple-endpoints-at-a-single-listenuri.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-129">[Multiple Endpoints at a Single ListenUri](multiple-endpoints-at-a-single-listenuri.md)\\</span></span>
<span data-ttu-id="fa307-130">Показана служба, в которой размещается несколько конечных точек по одному адресу `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="fa307-130">Demonstrates a service that hosts multiple endpoints at a single `ListenUri`.</span></span>

- <span data-ttu-id="fa307-131">[OperationContextScope](operationcontextscope.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-131">[OperationContextScope](operationcontextscope.md)\\</span></span>
<span data-ttu-id="fa307-132">Демонстрируется способ отправки дополнительной информации при вызове функции WCF с помощью заголовков.</span><span class="sxs-lookup"><span data-stu-id="fa307-132">Demonstrates how to send extra information on a WCF call using headers.</span></span>

- <span data-ttu-id="fa307-133">[Описание службы](service-description.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-133">[Service Description](service-description.md)\\</span></span>
<span data-ttu-id="fa307-134">Демонстрируется процесс извлечения службой данных описания службы в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="fa307-134">Demonstrates how a service can retrieve its service description information at runtime.</span></span>

- <span data-ttu-id="fa307-135">[ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)\\</span><span class="sxs-lookup"><span data-stu-id="fa307-135">[ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)\\</span></span>
<span data-ttu-id="fa307-136">Демонстрируется использование повторного входа режима параллелизма в реализации службы.</span><span class="sxs-lookup"><span data-stu-id="fa307-136">Demonstrates how to use the Reentrant concurrency mode on a service implementation.</span></span>