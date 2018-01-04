---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d948d1c77fc3f188694062ca9dcb3058f408c45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="serviceappdomain"></a><span data-ttu-id="04d9f-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="04d9f-102">ServiceAppDomain</span></span>
<span data-ttu-id="04d9f-103">Сопоставляет службу с доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="04d9f-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04d9f-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="04d9f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="04d9f-105">Methods</span></span>  
 <span data-ttu-id="04d9f-106">Класс ServiceAppDomain не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="04d9f-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="04d9f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="04d9f-107">Properties</span></span>  
 <span data-ttu-id="04d9f-108">Класс ServiceAppDomain имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="04d9f-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="04d9f-109">ref</span><span class="sxs-lookup"><span data-stu-id="04d9f-109">ref</span></span>  
 <span data-ttu-id="04d9f-110">Тип данных: Service</span><span class="sxs-lookup"><span data-stu-id="04d9f-110">Data type: Service</span></span>  
<span data-ttu-id="04d9f-111">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="04d9f-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="04d9f-112">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="04d9f-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04d9f-113">Служба этого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="04d9f-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="04d9f-114">ref</span><span class="sxs-lookup"><span data-stu-id="04d9f-114">ref</span></span>  
 <span data-ttu-id="04d9f-115">Тип данных: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="04d9f-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="04d9f-116">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="04d9f-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="04d9f-117">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="04d9f-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="04d9f-118">Содержит свойства домена приложения.</span><span class="sxs-lookup"><span data-stu-id="04d9f-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04d9f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="04d9f-119">Requirements</span></span>  
  
|<span data-ttu-id="04d9f-120">MOF</span><span class="sxs-lookup"><span data-stu-id="04d9f-120">MOF</span></span>|<span data-ttu-id="04d9f-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="04d9f-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="04d9f-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="04d9f-122">Namespace</span></span>|<span data-ttu-id="04d9f-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="04d9f-123">Defined in root\ServiceModel</span></span>|
