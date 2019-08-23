---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942414"
---
# <a name="servicecertificate"></a><span data-ttu-id="476b9-101">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="476b9-101">\<serviceCertificate></span></span>
<span data-ttu-id="476b9-102">Настраивает сертификат X. 509, используемый для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="476b9-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="476b9-103">\<> System. identityModel. Services</span><span class="sxs-lookup"><span data-stu-id="476b9-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="476b9-104">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="476b9-104">\<federationConfiguration></span></span>  
<span data-ttu-id="476b9-105">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="476b9-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="476b9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="476b9-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="476b9-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="476b9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="476b9-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="476b9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="476b9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="476b9-109">Attributes</span></span>  
 <span data-ttu-id="476b9-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="476b9-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="476b9-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="476b9-111">Child Elements</span></span>  
  
|<span data-ttu-id="476b9-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="476b9-112">Element</span></span>|<span data-ttu-id="476b9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="476b9-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="476b9-114">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="476b9-114">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="476b9-115">Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="476b9-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="476b9-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="476b9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="476b9-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="476b9-117">Element</span></span>|<span data-ttu-id="476b9-118">Описание</span><span class="sxs-lookup"><span data-stu-id="476b9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="476b9-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="476b9-119">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="476b9-120">Содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> свойства (всфам) <xref:System.IdentityModel.Services.SessionAuthenticationModule> и (SAM).</span><span class="sxs-lookup"><span data-stu-id="476b9-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="476b9-121">Пример</span><span class="sxs-lookup"><span data-stu-id="476b9-121">Example</span></span>  
 <span data-ttu-id="476b9-122">В следующем коде XML показано использование \<элемента > serviceCertificate.</span><span class="sxs-lookup"><span data-stu-id="476b9-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="476b9-123">XML взят из `CustomToken` примера.</span><span class="sxs-lookup"><span data-stu-id="476b9-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
