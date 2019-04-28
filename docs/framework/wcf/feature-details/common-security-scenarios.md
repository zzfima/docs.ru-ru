---
title: Типовые сценарии безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: af58d6b529fba32380bedb9a892a2b1fd4807d96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857575"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="905dc-102">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="905dc-102">Common Security Scenarios</span></span>
<span data-ttu-id="905dc-103">В подразделах этого раздела рассматривается множество возможных конфигураций безопасности клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="905dc-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="905dc-104">Конфигурация зависит от ряда факторов:</span><span class="sxs-lookup"><span data-stu-id="905dc-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="905dc-105">например, находится ли служба или клиент в интрасети, или чем обеспечивается безопасность - Windows или транспортом (таким как HTTPS).</span><span class="sxs-lookup"><span data-stu-id="905dc-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="905dc-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="905dc-106">In This Section</span></span>  
 [<span data-ttu-id="905dc-107">Незащищенные интернет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="905dc-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="905dc-108">Пример общедоступных, незащищенных клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="905dc-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="905dc-109">Незащищенные интранет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="905dc-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="905dc-110">Базовой службы Windows Communication Foundation (WCF) разработан для предоставления информации о защищенной частной сети для приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="905dc-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="905dc-111">Безопасность транспорта с обычной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="905dc-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="905dc-112">Приложение, позволяющее клиентам входить в систему с использованием пользовательской проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="905dc-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="905dc-113">Безопасность транспорта с проверкой подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="905dc-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="905dc-114">Клиент и служба, защищенные механизмом безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="905dc-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="905dc-115">Безопасность транспорта с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="905dc-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="905dc-116">Сценарий с использованием механизма безопасности транспорта (такого как HTTPS) для обеспечения конфиденциальности и целостности.</span><span class="sxs-lookup"><span data-stu-id="905dc-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="905dc-117">Безопасность транспорта с проверкой подлинности с использованием сертификатов</span><span class="sxs-lookup"><span data-stu-id="905dc-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="905dc-118">Клиент и служба, защищенные сертификатом.</span><span class="sxs-lookup"><span data-stu-id="905dc-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="905dc-119">Безопасность сообщений с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="905dc-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="905dc-120">Показывает, клиент и служба, защищенные механизмом безопасности сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="905dc-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="905dc-121">Безопасность сообщений при использовании клиентом учетных данных пользователя</span><span class="sxs-lookup"><span data-stu-id="905dc-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="905dc-122">Клиент - приложение Windows Forms, позволяющее клиентам входить в систему с использованием имени пользователя и пароля домена.</span><span class="sxs-lookup"><span data-stu-id="905dc-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="905dc-123">Безопасность сообщений при использовании клиентом сертификата</span><span class="sxs-lookup"><span data-stu-id="905dc-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="905dc-124">Серверы имеют сертификаты и каждый клиент имеет сертификат.</span><span class="sxs-lookup"><span data-stu-id="905dc-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="905dc-125">Контекст безопасности устанавливается посредством согласования по протоколу TLS.</span><span class="sxs-lookup"><span data-stu-id="905dc-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="905dc-126">Безопасность сообщений с клиентом Windows</span><span class="sxs-lookup"><span data-stu-id="905dc-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="905dc-127">Разновидность клиента с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="905dc-127">A variation of the certificate client.</span></span> <span data-ttu-id="905dc-128">Серверы имеют сертификаты и каждый клиент имеет сертификат.</span><span class="sxs-lookup"><span data-stu-id="905dc-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="905dc-129">Контекст безопасности устанавливается посредством согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="905dc-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="905dc-130">Безопасность сообщений с использованием клиента Windows без согласования учетных данных</span><span class="sxs-lookup"><span data-stu-id="905dc-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="905dc-131">Клиент и служба, защищенные доменом Kerberos.</span><span class="sxs-lookup"><span data-stu-id="905dc-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="905dc-132">Безопасность сообщений с взаимными сертификатами</span><span class="sxs-lookup"><span data-stu-id="905dc-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="905dc-133">Серверы имеют сертификаты и каждый клиент имеет сертификат.</span><span class="sxs-lookup"><span data-stu-id="905dc-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="905dc-134">Сертификат сервера распространяется вместе с приложением и доступен внештатно.</span><span class="sxs-lookup"><span data-stu-id="905dc-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="905dc-135">Безопасность сообщений с использованием выданных маркеров</span><span class="sxs-lookup"><span data-stu-id="905dc-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="905dc-136">Федеративная безопасность, позволяющая установить доверие между независимыми доменами.</span><span class="sxs-lookup"><span data-stu-id="905dc-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="905dc-137">Доверенная подсистема</span><span class="sxs-lookup"><span data-stu-id="905dc-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="905dc-138">Клиент обращается к одной или нескольким веб-службам, распределенным по сети.</span><span class="sxs-lookup"><span data-stu-id="905dc-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="905dc-139">Веб-службы обращаются к дополнительным ресурсам (таким как базы данных или другие веб-службы), которые должны быть защищены.</span><span class="sxs-lookup"><span data-stu-id="905dc-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="905dc-140">Ссылка</span><span class="sxs-lookup"><span data-stu-id="905dc-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="905dc-141">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="905dc-141">Related Sections</span></span>  
 [<span data-ttu-id="905dc-142">Авторизация</span><span class="sxs-lookup"><span data-stu-id="905dc-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="905dc-143">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="905dc-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="905dc-144">Безопасность</span><span class="sxs-lookup"><span data-stu-id="905dc-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="905dc-145">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="905dc-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="905dc-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="905dc-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="905dc-147">Authentication</span><span class="sxs-lookup"><span data-stu-id="905dc-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="905dc-148">Авторизация</span><span class="sxs-lookup"><span data-stu-id="905dc-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="905dc-149">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="905dc-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="905dc-150">Аудит</span><span class="sxs-lookup"><span data-stu-id="905dc-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="905dc-151">См. также</span><span class="sxs-lookup"><span data-stu-id="905dc-151">See also</span></span>

- [<span data-ttu-id="905dc-152">Руководство и рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="905dc-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [<span data-ttu-id="905dc-153">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="905dc-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
