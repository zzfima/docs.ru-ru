---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: 18100ac36b5116c2373171ff795fc23b75bbd6f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572124"
---
# <a name="servicecredentials"></a><span data-ttu-id="c8ad3-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="c8ad3-102">ServiceCredentials</span></span>
<span data-ttu-id="c8ad3-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="c8ad3-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8ad3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8ad3-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c8ad3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c8ad3-105">Methods</span></span>  
 <span data-ttu-id="c8ad3-106">Класс ServiceCredentials не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c8ad3-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c8ad3-107">Properties</span></span>  
 <span data-ttu-id="c8ad3-108">Класс ServiceCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="c8ad3-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="c8ad3-109">ClientCertificate</span></span>  
 <span data-ttu-id="c8ad3-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c8ad3-110">Data type: string</span></span>  
  
 <span data-ttu-id="c8ad3-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="c8ad3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c8ad3-112">Параметры проверки подлинности сертификата клиента и подготовки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="c8ad3-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="c8ad3-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="c8ad3-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c8ad3-114">Data type: string</span></span>  
  
 <span data-ttu-id="c8ad3-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="c8ad3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c8ad3-116">Параметры проверки подлинности текущего выданного маркера для этой службы.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="c8ad3-117">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="c8ad3-117">Peer</span></span>  
 <span data-ttu-id="c8ad3-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c8ad3-118">Data type: string</span></span>  
  
 <span data-ttu-id="c8ad3-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="c8ad3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c8ad3-120">Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="c8ad3-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="c8ad3-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="c8ad3-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c8ad3-122">Data type: string</span></span>  
  
 <span data-ttu-id="c8ad3-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="c8ad3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c8ad3-124">Задает текущие параметры безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="c8ad3-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="c8ad3-125">ServiceCertificate</span></span>  
 <span data-ttu-id="c8ad3-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c8ad3-126">Data type: string</span></span>  
  
 <span data-ttu-id="c8ad3-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="c8ad3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c8ad3-128">Сертификат, связанный с этой службой.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="c8ad3-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="c8ad3-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="c8ad3-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c8ad3-130">Data type: string</span></span>  
  
 <span data-ttu-id="c8ad3-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="c8ad3-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c8ad3-132">Параметры проверки имени пользователя и пароля для данной службы.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="c8ad3-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="c8ad3-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="c8ad3-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c8ad3-134">Data type: string</span></span>  
  
 <span data-ttu-id="c8ad3-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="c8ad3-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c8ad3-136">Параметры проверки подлинности Windows для этой службы.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8ad3-137">Требования</span><span class="sxs-lookup"><span data-stu-id="c8ad3-137">Requirements</span></span>  
  
|<span data-ttu-id="c8ad3-138">MOF</span><span class="sxs-lookup"><span data-stu-id="c8ad3-138">MOF</span></span>|<span data-ttu-id="c8ad3-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c8ad3-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c8ad3-140">Namespace</span></span>|<span data-ttu-id="c8ad3-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c8ad3-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8ad3-142">См. также</span><span class="sxs-lookup"><span data-stu-id="c8ad3-142">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceCredentials>
