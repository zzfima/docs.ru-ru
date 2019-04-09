---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090918"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="54185-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="54185-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="54185-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="54185-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54185-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54185-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="54185-105">Методы</span><span class="sxs-lookup"><span data-stu-id="54185-105">Methods</span></span>  
 <span data-ttu-id="54185-106">Класс ServiceDebugBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="54185-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="54185-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="54185-107">Properties</span></span>  
 <span data-ttu-id="54185-108">Класс ServiceDebugBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="54185-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="54185-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="54185-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="54185-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="54185-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="54185-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="54185-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54185-112">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="54185-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="54185-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="54185-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="54185-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="54185-114">Data type: string</span></span>  
  
 <span data-ttu-id="54185-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="54185-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54185-116">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="54185-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="54185-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="54185-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="54185-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="54185-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="54185-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="54185-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54185-120">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="54185-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="54185-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="54185-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="54185-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="54185-122">Data type: string</span></span>  
  
 <span data-ttu-id="54185-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="54185-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54185-124">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="54185-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="54185-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="54185-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="54185-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="54185-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="54185-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="54185-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54185-128">Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.</span><span class="sxs-lookup"><span data-stu-id="54185-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54185-129">Требования</span><span class="sxs-lookup"><span data-stu-id="54185-129">Requirements</span></span>  
  
|<span data-ttu-id="54185-130">MOF</span><span class="sxs-lookup"><span data-stu-id="54185-130">MOF</span></span>|<span data-ttu-id="54185-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="54185-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="54185-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="54185-132">Namespace</span></span>|<span data-ttu-id="54185-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="54185-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54185-134">См. также</span><span class="sxs-lookup"><span data-stu-id="54185-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
