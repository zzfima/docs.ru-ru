---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485672"
---
# <a name="serviceappdomain"></a><span data-ttu-id="e7a69-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="e7a69-102">ServiceAppDomain</span></span>
<span data-ttu-id="e7a69-103">Сопоставляет службу с доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="e7a69-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7a69-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e7a69-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e7a69-105">Methods</span></span>  
 <span data-ttu-id="e7a69-106">Класс ServiceAppDomain не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="e7a69-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e7a69-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e7a69-107">Properties</span></span>  
 <span data-ttu-id="e7a69-108">Класс ServiceAppDomain имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="e7a69-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e7a69-109">ref</span><span class="sxs-lookup"><span data-stu-id="e7a69-109">ref</span></span>  
 <span data-ttu-id="e7a69-110">Тип данных: Service</span><span class="sxs-lookup"><span data-stu-id="e7a69-110">Data type: Service</span></span>  
<span data-ttu-id="e7a69-111">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="e7a69-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="e7a69-112">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e7a69-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7a69-113">Служба этого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e7a69-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e7a69-114">ref</span><span class="sxs-lookup"><span data-stu-id="e7a69-114">ref</span></span>  
 <span data-ttu-id="e7a69-115">Тип данных: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="e7a69-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="e7a69-116">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="e7a69-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="e7a69-117">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e7a69-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7a69-118">Содержит свойства домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e7a69-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7a69-119">Требования</span><span class="sxs-lookup"><span data-stu-id="e7a69-119">Requirements</span></span>  
  
|<span data-ttu-id="e7a69-120">MOF</span><span class="sxs-lookup"><span data-stu-id="e7a69-120">MOF</span></span>|<span data-ttu-id="e7a69-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e7a69-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e7a69-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e7a69-122">Namespace</span></span>|<span data-ttu-id="e7a69-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e7a69-123">Defined in root\ServiceModel</span></span>|
