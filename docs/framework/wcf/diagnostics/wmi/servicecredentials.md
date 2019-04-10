---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230932"
---
# <a name="servicecredentials"></a><span data-ttu-id="f502b-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="f502b-102">ServiceCredentials</span></span>
<span data-ttu-id="f502b-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="f502b-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f502b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f502b-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="f502b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f502b-105">Methods</span></span>  
 <span data-ttu-id="f502b-106">Класс ServiceCredentials не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="f502b-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f502b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f502b-107">Properties</span></span>  
 <span data-ttu-id="f502b-108">Класс ServiceCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f502b-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="f502b-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="f502b-109">ClientCertificate</span></span>  
 <span data-ttu-id="f502b-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f502b-110">Data type: string</span></span>  
  
 <span data-ttu-id="f502b-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f502b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f502b-112">Параметры проверки подлинности сертификата клиента и подготовки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="f502b-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="f502b-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="f502b-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="f502b-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f502b-114">Data type: string</span></span>  
  
 <span data-ttu-id="f502b-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f502b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f502b-116">Параметры проверки подлинности текущего выданного маркера для этой службы.</span><span class="sxs-lookup"><span data-stu-id="f502b-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="f502b-117">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="f502b-117">Peer</span></span>  
 <span data-ttu-id="f502b-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f502b-118">Data type: string</span></span>  
  
 <span data-ttu-id="f502b-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f502b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f502b-120">Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="f502b-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="f502b-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="f502b-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="f502b-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f502b-122">Data type: string</span></span>  
  
 <span data-ttu-id="f502b-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f502b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f502b-124">Задает текущие параметры безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="f502b-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="f502b-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="f502b-125">ServiceCertificate</span></span>  
 <span data-ttu-id="f502b-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f502b-126">Data type: string</span></span>  
  
 <span data-ttu-id="f502b-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f502b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f502b-128">Сертификат, связанный с этой службой.</span><span class="sxs-lookup"><span data-stu-id="f502b-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="f502b-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="f502b-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="f502b-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f502b-130">Data type: string</span></span>  
  
 <span data-ttu-id="f502b-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f502b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f502b-132">Параметры проверки имени пользователя и пароля для данной службы.</span><span class="sxs-lookup"><span data-stu-id="f502b-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="f502b-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="f502b-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="f502b-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f502b-134">Data type: string</span></span>  
  
 <span data-ttu-id="f502b-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f502b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f502b-136">Параметры проверки подлинности Windows для этой службы.</span><span class="sxs-lookup"><span data-stu-id="f502b-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f502b-137">Требования</span><span class="sxs-lookup"><span data-stu-id="f502b-137">Requirements</span></span>  
  
|<span data-ttu-id="f502b-138">MOF</span><span class="sxs-lookup"><span data-stu-id="f502b-138">MOF</span></span>|<span data-ttu-id="f502b-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f502b-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f502b-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f502b-140">Namespace</span></span>|<span data-ttu-id="f502b-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f502b-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f502b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f502b-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
