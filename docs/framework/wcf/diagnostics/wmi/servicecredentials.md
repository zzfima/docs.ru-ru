---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89aff21ed916e1b486a191f86dde5ed8b3e4ba22
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="65ee1-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="65ee1-102">ServiceCredentials</span></span>
<span data-ttu-id="65ee1-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="65ee1-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65ee1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65ee1-104">Syntax</span></span>  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="65ee1-105">Методы</span><span class="sxs-lookup"><span data-stu-id="65ee1-105">Methods</span></span>  
 <span data-ttu-id="65ee1-106">Класс ServiceCredentials не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="65ee1-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="65ee1-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="65ee1-107">Properties</span></span>  
 <span data-ttu-id="65ee1-108">Класс ServiceCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="65ee1-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="65ee1-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="65ee1-109">ClientCertificate</span></span>  
 <span data-ttu-id="65ee1-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="65ee1-110">Data type: string</span></span>  
  
 <span data-ttu-id="65ee1-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="65ee1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65ee1-112">Параметры проверки подлинности сертификата клиента и подготовки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="65ee1-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="65ee1-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="65ee1-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="65ee1-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="65ee1-114">Data type: string</span></span>  
  
 <span data-ttu-id="65ee1-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="65ee1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65ee1-116">Параметры проверки подлинности текущего выданного маркера для этой службы.</span><span class="sxs-lookup"><span data-stu-id="65ee1-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="65ee1-117">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="65ee1-117">Peer</span></span>  
 <span data-ttu-id="65ee1-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="65ee1-118">Data type: string</span></span>  
  
 <span data-ttu-id="65ee1-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="65ee1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65ee1-120">Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="65ee1-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="65ee1-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="65ee1-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="65ee1-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="65ee1-122">Data type: string</span></span>  
  
 <span data-ttu-id="65ee1-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="65ee1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65ee1-124">Задает текущие параметры безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="65ee1-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="65ee1-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="65ee1-125">ServiceCertificate</span></span>  
 <span data-ttu-id="65ee1-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="65ee1-126">Data type: string</span></span>  
  
 <span data-ttu-id="65ee1-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="65ee1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65ee1-128">Сертификат, связанный с этой службой.</span><span class="sxs-lookup"><span data-stu-id="65ee1-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="65ee1-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="65ee1-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="65ee1-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="65ee1-130">Data type: string</span></span>  
  
 <span data-ttu-id="65ee1-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="65ee1-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65ee1-132">Параметры проверки имени пользователя и пароля для данной службы.</span><span class="sxs-lookup"><span data-stu-id="65ee1-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="65ee1-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="65ee1-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="65ee1-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="65ee1-134">Data type: string</span></span>  
  
 <span data-ttu-id="65ee1-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="65ee1-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="65ee1-136">Параметры проверки подлинности Windows для этой службы.</span><span class="sxs-lookup"><span data-stu-id="65ee1-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65ee1-137">Требования</span><span class="sxs-lookup"><span data-stu-id="65ee1-137">Requirements</span></span>  
  
|<span data-ttu-id="65ee1-138">MOF</span><span class="sxs-lookup"><span data-stu-id="65ee1-138">MOF</span></span>|<span data-ttu-id="65ee1-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="65ee1-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="65ee1-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="65ee1-140">Namespace</span></span>|<span data-ttu-id="65ee1-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="65ee1-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65ee1-142">См. также</span><span class="sxs-lookup"><span data-stu-id="65ee1-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
