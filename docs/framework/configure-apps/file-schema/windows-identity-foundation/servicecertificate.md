---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766781"
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="8c8dc-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="8c8dc-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="8c8dc-103">Настраивает сертификат X.509, используемый для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="8c8dc-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="8c8dc-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="8c8dc-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="8c8dc-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8c8dc-105">\<federationConfiguration></span></span>  
<span data-ttu-id="8c8dc-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="8c8dc-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8dc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c8dc-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c8dc-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8c8dc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8c8dc-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8c8dc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c8dc-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c8dc-110">Attributes</span></span>  
 <span data-ttu-id="8c8dc-111">Нет</span><span class="sxs-lookup"><span data-stu-id="8c8dc-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c8dc-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c8dc-112">Child Elements</span></span>  
  
|<span data-ttu-id="8c8dc-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c8dc-113">Element</span></span>|<span data-ttu-id="8c8dc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8c8dc-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c8dc-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="8c8dc-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="8c8dc-116">Указывает параметры, используемые для поиска и проверки сертификатов в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="8c8dc-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c8dc-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c8dc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8c8dc-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c8dc-118">Element</span></span>|<span data-ttu-id="8c8dc-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8c8dc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c8dc-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="8c8dc-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="8c8dc-121">Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="8c8dc-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c8dc-122">Пример</span><span class="sxs-lookup"><span data-stu-id="8c8dc-122">Example</span></span>  
 <span data-ttu-id="8c8dc-123">Следующий XML-КОДЕ показано использование \<serviceCertificate > элемента.</span><span class="sxs-lookup"><span data-stu-id="8c8dc-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="8c8dc-124">XML-код будет браться из `CustomToken` образца.</span><span class="sxs-lookup"><span data-stu-id="8c8dc-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
