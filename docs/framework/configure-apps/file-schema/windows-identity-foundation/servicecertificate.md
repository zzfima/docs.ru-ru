---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 328d074f9edc5ddf871308a7e3d694bf94adea78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793826"
---
# <a name="servicecertificate"></a><span data-ttu-id="46904-101">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="46904-101">\<serviceCertificate></span></span>
<span data-ttu-id="46904-102">Настраивает сертификат X.509, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="46904-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="46904-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="46904-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="46904-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="46904-104">\<federationConfiguration></span></span>  
<span data-ttu-id="46904-105">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="46904-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46904-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46904-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46904-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46904-107">Attributes and Elements</span></span>  
 <span data-ttu-id="46904-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46904-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46904-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46904-109">Attributes</span></span>  
 <span data-ttu-id="46904-110">Нет</span><span class="sxs-lookup"><span data-stu-id="46904-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46904-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46904-111">Child Elements</span></span>  
  
|<span data-ttu-id="46904-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="46904-112">Element</span></span>|<span data-ttu-id="46904-113">Описание</span><span class="sxs-lookup"><span data-stu-id="46904-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46904-114">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="46904-114">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="46904-115">Задает параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="46904-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46904-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46904-116">Parent Elements</span></span>  
  
|<span data-ttu-id="46904-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="46904-117">Element</span></span>|<span data-ttu-id="46904-118">Описание</span><span class="sxs-lookup"><span data-stu-id="46904-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46904-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="46904-119">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="46904-120">Содержит параметры, определяющие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="46904-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46904-121">Пример</span><span class="sxs-lookup"><span data-stu-id="46904-121">Example</span></span>  
 <span data-ttu-id="46904-122">Следующий код XML показывает использование \<serviceCertificate > элемента.</span><span class="sxs-lookup"><span data-stu-id="46904-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="46904-123">XML-код взят из `CustomToken` образца.</span><span class="sxs-lookup"><span data-stu-id="46904-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
