---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: 8b6200f84f352d49cf142d9c8b97d1c2b36149b2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180904"
---
# <a name="clientcredentials"></a><span data-ttu-id="996be-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="996be-102">ClientCredentials</span></span>
<span data-ttu-id="996be-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="996be-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="996be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="996be-104">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="996be-105">Методы</span><span class="sxs-lookup"><span data-stu-id="996be-105">Methods</span></span>  
 <span data-ttu-id="996be-106">Класс ClientCredentials не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="996be-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="996be-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="996be-107">Properties</span></span>  
 <span data-ttu-id="996be-108">Класс ClientCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="996be-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="996be-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="996be-109">ClientCertificate</span></span>  
 <span data-ttu-id="996be-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="996be-110">Data type: string</span></span>  
  
 <span data-ttu-id="996be-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-112">Сертификат X.509, используемый клиентом для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="996be-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="996be-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="996be-113">HttpDigest</span></span>  
 <span data-ttu-id="996be-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="996be-114">Data type: string</span></span>  
  
 <span data-ttu-id="996be-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-116">Текущие учетные данные дайджеста HTTP.</span><span class="sxs-lookup"><span data-stu-id="996be-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="996be-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="996be-117">IssuedToken</span></span>  
 <span data-ttu-id="996be-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="996be-118">Data type: string</span></span>  
  
 <span data-ttu-id="996be-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-120">Адрес конечной точки и привязка, используемые для связи с локальной службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="996be-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="996be-121">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="996be-121">Peer</span></span>  
 <span data-ttu-id="996be-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="996be-122">Data type: string</span></span>  
  
 <span data-ttu-id="996be-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-124">Учетные данные, используемые одноранговым узлом для подтверждения своей подлинности при подключении к другим узлам в сетке.</span><span class="sxs-lookup"><span data-stu-id="996be-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="996be-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="996be-125">ServiceCertificate</span></span>  
 <span data-ttu-id="996be-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="996be-126">Data type: string</span></span>  
  
 <span data-ttu-id="996be-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-128">Сертификат X.509 службы.</span><span class="sxs-lookup"><span data-stu-id="996be-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="996be-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="996be-129">SupportInteractive</span></span>  
 <span data-ttu-id="996be-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="996be-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="996be-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-132">Логическое значение, определяющее, поддерживают ли учетные данные интерактивное согласование.</span><span class="sxs-lookup"><span data-stu-id="996be-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="996be-133">UserName</span><span class="sxs-lookup"><span data-stu-id="996be-133">UserName</span></span>  
 <span data-ttu-id="996be-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="996be-134">Data type: string</span></span>  
  
 <span data-ttu-id="996be-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-136">Имя пользователя и пароль, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="996be-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="996be-137">Windows</span><span class="sxs-lookup"><span data-stu-id="996be-137">Windows</span></span>  
 <span data-ttu-id="996be-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="996be-138">Data type: string</span></span>  
  
 <span data-ttu-id="996be-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="996be-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="996be-140">Учетные данные Windows, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="996be-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="996be-141">Требования</span><span class="sxs-lookup"><span data-stu-id="996be-141">Requirements</span></span>  
  
|<span data-ttu-id="996be-142">MOF</span><span class="sxs-lookup"><span data-stu-id="996be-142">MOF</span></span>|<span data-ttu-id="996be-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="996be-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="996be-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="996be-144">Namespace</span></span>|<span data-ttu-id="996be-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="996be-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="996be-146">См. также</span><span class="sxs-lookup"><span data-stu-id="996be-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>
