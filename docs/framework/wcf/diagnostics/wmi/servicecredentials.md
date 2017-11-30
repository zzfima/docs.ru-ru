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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4cc9d7d7d46157b7df202c6daffb31b90fa98c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="c77ee-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="c77ee-102">ServiceCredentials</span></span>
<span data-ttu-id="c77ee-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="c77ee-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c77ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c77ee-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c77ee-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c77ee-105">Methods</span></span>  
 <span data-ttu-id="c77ee-106">Класс ServiceCredentials не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="c77ee-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c77ee-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c77ee-107">Properties</span></span>  
 <span data-ttu-id="c77ee-108">Класс ServiceCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c77ee-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="c77ee-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="c77ee-109">ClientCertificate</span></span>  
 <span data-ttu-id="c77ee-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c77ee-110">Data type: string</span></span>  
  
 <span data-ttu-id="c77ee-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c77ee-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c77ee-112">Параметры проверки подлинности сертификата клиента и подготовки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="c77ee-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="c77ee-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="c77ee-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="c77ee-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c77ee-114">Data type: string</span></span>  
  
 <span data-ttu-id="c77ee-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c77ee-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c77ee-116">Параметры проверки подлинности текущего выданного маркера для этой службы.</span><span class="sxs-lookup"><span data-stu-id="c77ee-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="c77ee-117">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="c77ee-117">Peer</span></span>  
 <span data-ttu-id="c77ee-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c77ee-118">Data type: string</span></span>  
  
 <span data-ttu-id="c77ee-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c77ee-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c77ee-120">Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="c77ee-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="c77ee-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="c77ee-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="c77ee-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c77ee-122">Data type: string</span></span>  
  
 <span data-ttu-id="c77ee-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c77ee-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c77ee-124">Задает текущие параметры безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="c77ee-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="c77ee-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="c77ee-125">ServiceCertificate</span></span>  
 <span data-ttu-id="c77ee-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c77ee-126">Data type: string</span></span>  
  
 <span data-ttu-id="c77ee-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c77ee-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c77ee-128">Сертификат, связанный с этой службой.</span><span class="sxs-lookup"><span data-stu-id="c77ee-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="c77ee-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="c77ee-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="c77ee-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c77ee-130">Data type: string</span></span>  
  
 <span data-ttu-id="c77ee-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c77ee-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c77ee-132">Параметры проверки имени пользователя и пароля для данной службы.</span><span class="sxs-lookup"><span data-stu-id="c77ee-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="c77ee-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="c77ee-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="c77ee-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c77ee-134">Data type: string</span></span>  
  
 <span data-ttu-id="c77ee-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c77ee-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c77ee-136">Параметры проверки подлинности Windows для этой службы.</span><span class="sxs-lookup"><span data-stu-id="c77ee-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c77ee-137">Требования</span><span class="sxs-lookup"><span data-stu-id="c77ee-137">Requirements</span></span>  
  
|<span data-ttu-id="c77ee-138">MOF</span><span class="sxs-lookup"><span data-stu-id="c77ee-138">MOF</span></span>|<span data-ttu-id="c77ee-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c77ee-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c77ee-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c77ee-140">Namespace</span></span>|<span data-ttu-id="c77ee-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c77ee-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c77ee-142">См. также</span><span class="sxs-lookup"><span data-stu-id="c77ee-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
