---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957077"
---
# <a name="serviceappdomain"></a><span data-ttu-id="9f2e3-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f2e3-102">ServiceAppDomain</span></span>
<span data-ttu-id="9f2e3-103">Сопоставляет службу с доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="9f2e3-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f2e3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f2e3-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9f2e3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9f2e3-105">Methods</span></span>  
 <span data-ttu-id="9f2e3-106">Класс ServiceAppDomain не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="9f2e3-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9f2e3-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="9f2e3-107">Properties</span></span>  
 <span data-ttu-id="9f2e3-108">Класс ServiceAppDomain имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9f2e3-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9f2e3-109">ref</span><span class="sxs-lookup"><span data-stu-id="9f2e3-109">ref</span></span>  
 <span data-ttu-id="9f2e3-110">Тип данных: Служба</span><span class="sxs-lookup"><span data-stu-id="9f2e3-110">Data type: Service</span></span>  
<span data-ttu-id="9f2e3-111">Квалификаторы: Ключ</span><span class="sxs-lookup"><span data-stu-id="9f2e3-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="9f2e3-112">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9f2e3-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f2e3-113">Служба этого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9f2e3-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9f2e3-114">ref</span><span class="sxs-lookup"><span data-stu-id="9f2e3-114">ref</span></span>  
 <span data-ttu-id="9f2e3-115">Тип данных: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="9f2e3-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="9f2e3-116">Квалификаторы: Ключ</span><span class="sxs-lookup"><span data-stu-id="9f2e3-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="9f2e3-117">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9f2e3-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f2e3-118">Содержит свойства домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9f2e3-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f2e3-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9f2e3-119">Requirements</span></span>  
  
|<span data-ttu-id="9f2e3-120">MOF</span><span class="sxs-lookup"><span data-stu-id="9f2e3-120">MOF</span></span>|<span data-ttu-id="9f2e3-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9f2e3-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9f2e3-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9f2e3-122">Namespace</span></span>|<span data-ttu-id="9f2e3-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="9f2e3-123">Defined in root\ServiceModel</span></span>|
