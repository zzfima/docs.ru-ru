---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192243"
---
# <a name="serviceappdomain"></a><span data-ttu-id="7f280-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="7f280-102">ServiceAppDomain</span></span>
<span data-ttu-id="7f280-103">Сопоставляет службу с доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="7f280-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f280-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f280-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7f280-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7f280-105">Methods</span></span>  
 <span data-ttu-id="7f280-106">Класс ServiceAppDomain не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="7f280-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7f280-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="7f280-107">Properties</span></span>  
 <span data-ttu-id="7f280-108">Класс ServiceAppDomain имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7f280-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="7f280-109">ref</span><span class="sxs-lookup"><span data-stu-id="7f280-109">ref</span></span>  
 <span data-ttu-id="7f280-110">Тип данных: Service</span><span class="sxs-lookup"><span data-stu-id="7f280-110">Data type: Service</span></span>  
<span data-ttu-id="7f280-111">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="7f280-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="7f280-112">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7f280-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7f280-113">Служба этого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7f280-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="7f280-114">ref</span><span class="sxs-lookup"><span data-stu-id="7f280-114">ref</span></span>  
 <span data-ttu-id="7f280-115">Тип данных: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="7f280-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="7f280-116">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="7f280-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="7f280-117">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7f280-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7f280-118">Содержит свойства домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7f280-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f280-119">Требования</span><span class="sxs-lookup"><span data-stu-id="7f280-119">Requirements</span></span>  
  
|<span data-ttu-id="7f280-120">MOF</span><span class="sxs-lookup"><span data-stu-id="7f280-120">MOF</span></span>|<span data-ttu-id="7f280-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7f280-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7f280-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="7f280-122">Namespace</span></span>|<span data-ttu-id="7f280-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7f280-123">Defined in root\ServiceModel</span></span>|
