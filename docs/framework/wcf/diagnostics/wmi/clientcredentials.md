---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: aa852ff82c44a3b5009dbc70e1067face44cbbe9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="clientcredentials"></a><span data-ttu-id="f3789-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="f3789-102">ClientCredentials</span></span>
<span data-ttu-id="f3789-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="f3789-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3789-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3789-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="f3789-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f3789-105">Methods</span></span>  
 <span data-ttu-id="f3789-106">Класс ClientCredentials не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="f3789-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f3789-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f3789-107">Properties</span></span>  
 <span data-ttu-id="f3789-108">Класс ClientCredentials имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f3789-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="f3789-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="f3789-109">ClientCertificate</span></span>  
 <span data-ttu-id="f3789-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3789-110">Data type: string</span></span>  
  
 <span data-ttu-id="f3789-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-112">Сертификат X.509, используемый клиентом для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="f3789-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="f3789-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="f3789-113">HttpDigest</span></span>  
 <span data-ttu-id="f3789-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3789-114">Data type: string</span></span>  
  
 <span data-ttu-id="f3789-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-116">Текущие учетные данные дайджеста HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3789-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="f3789-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="f3789-117">IssuedToken</span></span>  
 <span data-ttu-id="f3789-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3789-118">Data type: string</span></span>  
  
 <span data-ttu-id="f3789-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-120">Адрес конечной точки и привязка, используемые для связи с локальной службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f3789-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="f3789-121">Одноранговый узел</span><span class="sxs-lookup"><span data-stu-id="f3789-121">Peer</span></span>  
 <span data-ttu-id="f3789-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3789-122">Data type: string</span></span>  
  
 <span data-ttu-id="f3789-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-124">Учетные данные, используемые одноранговым узлом для подтверждения своей подлинности при подключении к другим узлам в сетке.</span><span class="sxs-lookup"><span data-stu-id="f3789-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="f3789-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="f3789-125">ServiceCertificate</span></span>  
 <span data-ttu-id="f3789-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3789-126">Data type: string</span></span>  
  
 <span data-ttu-id="f3789-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-128">Сертификат X.509 службы.</span><span class="sxs-lookup"><span data-stu-id="f3789-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="f3789-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="f3789-129">SupportInteractive</span></span>  
 <span data-ttu-id="f3789-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f3789-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="f3789-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-132">Логическое значение, определяющее, поддерживают ли учетные данные интерактивное согласование.</span><span class="sxs-lookup"><span data-stu-id="f3789-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="f3789-133">UserName</span><span class="sxs-lookup"><span data-stu-id="f3789-133">UserName</span></span>  
 <span data-ttu-id="f3789-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3789-134">Data type: string</span></span>  
  
 <span data-ttu-id="f3789-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-136">Имя пользователя и пароль, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="f3789-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="f3789-137">Windows</span><span class="sxs-lookup"><span data-stu-id="f3789-137">Windows</span></span>  
 <span data-ttu-id="f3789-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3789-138">Data type: string</span></span>  
  
 <span data-ttu-id="f3789-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f3789-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3789-140">Учетные данные Windows, используемые клиентом для подтверждения своей подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="f3789-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3789-141">Требования</span><span class="sxs-lookup"><span data-stu-id="f3789-141">Requirements</span></span>  
  
|<span data-ttu-id="f3789-142">MOF</span><span class="sxs-lookup"><span data-stu-id="f3789-142">MOF</span></span>|<span data-ttu-id="f3789-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f3789-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f3789-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f3789-144">Namespace</span></span>|<span data-ttu-id="f3789-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f3789-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3789-146">См. также</span><span class="sxs-lookup"><span data-stu-id="f3789-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>
