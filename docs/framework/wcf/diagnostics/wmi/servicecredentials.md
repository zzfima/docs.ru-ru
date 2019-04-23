---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772106"
---
# <a name="servicecredentials"></a><span data-ttu-id="8ff88-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="8ff88-102">ServiceCredentials</span></span>
<span data-ttu-id="8ff88-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="8ff88-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ff88-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="8ff88-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8ff88-105">Methods</span></span>  
 <span data-ttu-id="8ff88-106">Класс ServiceCredentials не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="8ff88-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8ff88-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="8ff88-107">Properties</span></span>  
 <span data-ttu-id="8ff88-108">Класс ServiceCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="8ff88-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="8ff88-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="8ff88-109">ClientCertificate</span></span>  
 <span data-ttu-id="8ff88-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8ff88-110">Data type: string</span></span>  
  
 <span data-ttu-id="8ff88-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="8ff88-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ff88-112">Параметры проверки подлинности сертификата клиента и подготовки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="8ff88-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="8ff88-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="8ff88-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="8ff88-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8ff88-114">Data type: string</span></span>  
  
 <span data-ttu-id="8ff88-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="8ff88-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ff88-116">Параметры проверки подлинности текущего выданного маркера для этой службы.</span><span class="sxs-lookup"><span data-stu-id="8ff88-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="8ff88-117">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="8ff88-117">Peer</span></span>  
 <span data-ttu-id="8ff88-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8ff88-118">Data type: string</span></span>  
  
 <span data-ttu-id="8ff88-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="8ff88-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ff88-120">Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="8ff88-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="8ff88-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="8ff88-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="8ff88-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8ff88-122">Data type: string</span></span>  
  
 <span data-ttu-id="8ff88-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="8ff88-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ff88-124">Задает текущие параметры безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="8ff88-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="8ff88-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="8ff88-125">ServiceCertificate</span></span>  
 <span data-ttu-id="8ff88-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8ff88-126">Data type: string</span></span>  
  
 <span data-ttu-id="8ff88-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="8ff88-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ff88-128">Сертификат, связанный с этой службой.</span><span class="sxs-lookup"><span data-stu-id="8ff88-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="8ff88-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="8ff88-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="8ff88-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8ff88-130">Data type: string</span></span>  
  
 <span data-ttu-id="8ff88-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="8ff88-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ff88-132">Параметры проверки имени пользователя и пароля для данной службы.</span><span class="sxs-lookup"><span data-stu-id="8ff88-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="8ff88-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="8ff88-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="8ff88-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8ff88-134">Data type: string</span></span>  
  
 <span data-ttu-id="8ff88-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="8ff88-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ff88-136">Параметры проверки подлинности Windows для этой службы.</span><span class="sxs-lookup"><span data-stu-id="8ff88-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff88-137">Требования</span><span class="sxs-lookup"><span data-stu-id="8ff88-137">Requirements</span></span>  
  
|<span data-ttu-id="8ff88-138">MOF</span><span class="sxs-lookup"><span data-stu-id="8ff88-138">MOF</span></span>|<span data-ttu-id="8ff88-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8ff88-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8ff88-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8ff88-140">Namespace</span></span>|<span data-ttu-id="8ff88-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="8ff88-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ff88-142">См. также</span><span class="sxs-lookup"><span data-stu-id="8ff88-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
