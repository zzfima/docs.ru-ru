---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: bf906e09ae71d26f8e95877f1c545c0724d57b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="servicecredentials"></a><span data-ttu-id="61f75-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="61f75-102">ServiceCredentials</span></span>
<span data-ttu-id="61f75-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="61f75-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61f75-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="61f75-105">Методы</span><span class="sxs-lookup"><span data-stu-id="61f75-105">Methods</span></span>  
 <span data-ttu-id="61f75-106">Класс ServiceCredentials не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="61f75-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="61f75-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="61f75-107">Properties</span></span>  
 <span data-ttu-id="61f75-108">Класс ServiceCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="61f75-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="61f75-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="61f75-109">ClientCertificate</span></span>  
 <span data-ttu-id="61f75-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="61f75-110">Data type: string</span></span>  
  
 <span data-ttu-id="61f75-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="61f75-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61f75-112">Параметры проверки подлинности сертификата клиента и подготовки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="61f75-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="61f75-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="61f75-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="61f75-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="61f75-114">Data type: string</span></span>  
  
 <span data-ttu-id="61f75-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="61f75-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61f75-116">Параметры проверки подлинности текущего выданного маркера для этой службы.</span><span class="sxs-lookup"><span data-stu-id="61f75-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="61f75-117">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="61f75-117">Peer</span></span>  
 <span data-ttu-id="61f75-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="61f75-118">Data type: string</span></span>  
  
 <span data-ttu-id="61f75-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="61f75-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61f75-120">Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="61f75-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="61f75-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="61f75-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="61f75-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="61f75-122">Data type: string</span></span>  
  
 <span data-ttu-id="61f75-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="61f75-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61f75-124">Задает текущие параметры безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="61f75-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="61f75-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="61f75-125">ServiceCertificate</span></span>  
 <span data-ttu-id="61f75-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="61f75-126">Data type: string</span></span>  
  
 <span data-ttu-id="61f75-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="61f75-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61f75-128">Сертификат, связанный с этой службой.</span><span class="sxs-lookup"><span data-stu-id="61f75-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="61f75-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="61f75-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="61f75-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="61f75-130">Data type: string</span></span>  
  
 <span data-ttu-id="61f75-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="61f75-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61f75-132">Параметры проверки имени пользователя и пароля для данной службы.</span><span class="sxs-lookup"><span data-stu-id="61f75-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="61f75-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="61f75-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="61f75-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="61f75-134">Data type: string</span></span>  
  
 <span data-ttu-id="61f75-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="61f75-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61f75-136">Параметры проверки подлинности Windows для этой службы.</span><span class="sxs-lookup"><span data-stu-id="61f75-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61f75-137">Требования</span><span class="sxs-lookup"><span data-stu-id="61f75-137">Requirements</span></span>  
  
|<span data-ttu-id="61f75-138">MOF</span><span class="sxs-lookup"><span data-stu-id="61f75-138">MOF</span></span>|<span data-ttu-id="61f75-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="61f75-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="61f75-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="61f75-140">Namespace</span></span>|<span data-ttu-id="61f75-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="61f75-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61f75-142">См. также</span><span class="sxs-lookup"><span data-stu-id="61f75-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
