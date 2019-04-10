---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c3adc675bb6c1e9011459a88fd7dc8e8cf63a880
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226590"
---
# <a name="clientcredentials"></a><span data-ttu-id="6fa10-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="6fa10-102">ClientCredentials</span></span>
<span data-ttu-id="6fa10-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="6fa10-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fa10-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6fa10-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6fa10-105">Methods</span></span>  
 <span data-ttu-id="6fa10-106">Класс ClientCredentials не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="6fa10-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6fa10-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="6fa10-107">Properties</span></span>  
 <span data-ttu-id="6fa10-108">Класс ClientCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="6fa10-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="6fa10-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="6fa10-109">ClientCertificate</span></span>  
 <span data-ttu-id="6fa10-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6fa10-110">Data type: string</span></span>  
  
 <span data-ttu-id="6fa10-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-112">Сертификат X.509, используемый клиентом для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="6fa10-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="6fa10-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="6fa10-113">HttpDigest</span></span>  
 <span data-ttu-id="6fa10-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6fa10-114">Data type: string</span></span>  
  
 <span data-ttu-id="6fa10-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-116">Текущие учетные данные хэш-кода HTTP.</span><span class="sxs-lookup"><span data-stu-id="6fa10-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="6fa10-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="6fa10-117">IssuedToken</span></span>  
 <span data-ttu-id="6fa10-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6fa10-118">Data type: string</span></span>  
  
 <span data-ttu-id="6fa10-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-120">Адрес конечной точки и привязка, используемые для связи с локальной службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6fa10-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="6fa10-121">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="6fa10-121">Peer</span></span>  
 <span data-ttu-id="6fa10-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6fa10-122">Data type: string</span></span>  
  
 <span data-ttu-id="6fa10-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-124">Учетные данные, используемые одноранговым узлом для подтверждения своей подлинности при подключении к другим узлам в сетке.</span><span class="sxs-lookup"><span data-stu-id="6fa10-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="6fa10-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="6fa10-125">ServiceCertificate</span></span>  
 <span data-ttu-id="6fa10-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6fa10-126">Data type: string</span></span>  
  
 <span data-ttu-id="6fa10-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-128">Сертификат X.509 службы.</span><span class="sxs-lookup"><span data-stu-id="6fa10-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="6fa10-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="6fa10-129">SupportInteractive</span></span>  
 <span data-ttu-id="6fa10-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="6fa10-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="6fa10-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-132">Логическое значение, определяющее, поддерживают ли учетные данные интерактивное согласование.</span><span class="sxs-lookup"><span data-stu-id="6fa10-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="6fa10-133">UserName</span><span class="sxs-lookup"><span data-stu-id="6fa10-133">UserName</span></span>  
 <span data-ttu-id="6fa10-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6fa10-134">Data type: string</span></span>  
  
 <span data-ttu-id="6fa10-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-136">Имя пользователя и пароль, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="6fa10-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="6fa10-137">Windows</span><span class="sxs-lookup"><span data-stu-id="6fa10-137">Windows</span></span>  
 <span data-ttu-id="6fa10-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6fa10-138">Data type: string</span></span>  
  
 <span data-ttu-id="6fa10-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6fa10-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa10-140">Учетные данные Windows, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="6fa10-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa10-141">Требования</span><span class="sxs-lookup"><span data-stu-id="6fa10-141">Requirements</span></span>  
  
|<span data-ttu-id="6fa10-142">MOF</span><span class="sxs-lookup"><span data-stu-id="6fa10-142">MOF</span></span>|<span data-ttu-id="6fa10-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6fa10-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6fa10-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6fa10-144">Namespace</span></span>|<span data-ttu-id="6fa10-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="6fa10-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6fa10-146">См. также</span><span class="sxs-lookup"><span data-stu-id="6fa10-146">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
